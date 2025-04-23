# Implementação do Protótipo - EscolApp

Este documento apresenta a implementação de um protótipo básico do EscolApp, com foco nas funcionalidades essenciais para demonstração. O protótipo foi desenvolvido em Python utilizando o framework Kivy/KivyMD.

## Estrutura de Arquivos

```
projeto_escolapp/
├── main.py                 # Arquivo principal da aplicação
├── database/
│   ├── __init__.py
│   ├── db_helper.py        # Funções auxiliares para o banco de dados
│   └── models.py           # Definição das classes/modelos
├── screens/
│   ├── __init__.py
│   ├── login_screen.py     # Tela de login
│   ├── menu_screen.py      # Menu principal
│   ├── notas_screen.py     # Tela de notas
│   ├── frequencia_screen.py # Tela de frequência
│   └── comunicados_screen.py # Tela de comunicados
├── utils/
│   ├── __init__.py
│   └── helpers.py          # Funções auxiliares gerais
└── assets/
    ├── images/             # Imagens e ícones
    └── fonts/              # Fontes personalizadas
```

## Código Principal (main.py)

```python
from kivy.config import Config
# Configurações para otimizar o desempenho em dispositivos mais antigos
Config.set('graphics', 'width', '360')
Config.set('graphics', 'height', '640')
Config.set('kivy', 'exit_on_escape', '0')
Config.set('graphics', 'maxfps', '30')

from kivymd.app import MDApp
from kivy.uix.screenmanager import ScreenManager, Screen
from kivy.lang import Builder
from kivy.core.window import Window

# Importação das telas
from screens.login_screen import LoginScreen
from screens.menu_screen import MenuScreen
from screens.notas_screen import NotasScreen
from screens.frequencia_screen import FrequenciaScreen
from screens.comunicados_screen import ComunicadosScreen

# Inicialização do banco de dados
from database.db_helper import init_database

class EscolApp(MDApp):
    def build(self):
        # Configuração do tema
        self.theme_cls.primary_palette = "Blue"
        self.theme_cls.accent_palette = "Amber"
        self.theme_cls.theme_style = "Light"
        
        # Inicialização do banco de dados
        init_database()
        
        # Gerenciador de telas
        self.sm = ScreenManager()
        
        # Adição das telas
        self.sm.add_widget(LoginScreen(name='login'))
        self.sm.add_widget(MenuScreen(name='menu'))
        self.sm.add_widget(NotasScreen(name='notas'))
        self.sm.add_widget(FrequenciaScreen(name='frequencia'))
        self.sm.add_widget(ComunicadosScreen(name='comunicados'))
        
        return self.sm
    
    def on_start(self):
        # Verificar se há dados salvos de login
        # Se não houver, iniciar na tela de login
        self.sm.current = 'login'

if __name__ == '__main__':
    EscolApp().run()
```

## Tela de Login (login_screen.py)

```python
from kivymd.uix.screen import MDScreen
from kivymd.uix.button import MDRaisedButton
from kivymd.uix.textfield import MDTextField
from kivymd.uix.label import MDLabel
from kivy.uix.boxlayout import BoxLayout
from kivy.metrics import dp

class LoginScreen(MDScreen):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        
        # Layout principal
        layout = BoxLayout(orientation='vertical', padding=dp(20), spacing=dp(20))
        
        # Título do app
        title = MDLabel(
            text="EscolApp",
            halign="center",
            font_style="H4",
            size_hint_y=None,
            height=dp(80)
        )
        
        # Campo de usuário
        self.username = MDTextField(
            hint_text="Usuário",
            helper_text="Digite seu nome de usuário",
            helper_text_mode="on_focus",
            size_hint_x=None,
            width=dp(300),
            pos_hint={'center_x': 0.5}
        )
        
        # Campo de senha
        self.password = MDTextField(
            hint_text="Senha",
            helper_text="Digite sua senha",
            helper_text_mode="on_focus",
            password=True,
            size_hint_x=None,
            width=dp(300),
            pos_hint={'center_x': 0.5}
        )
        
        # Botão de login
        login_button = MDRaisedButton(
            text="ENTRAR",
            size_hint=(None, None),
            width=dp(300),
            height=dp(50),
            pos_hint={'center_x': 0.5},
            on_release=self.login
        )
        
        # Esqueci minha senha
        forgot_password = MDLabel(
            text="Esqueci minha senha",
            halign="center",
            theme_text_color="Secondary",
            size_hint_y=None,
            height=dp(30)
        )
        
        # Adicionar widgets ao layout
        layout.add_widget(title)
        layout.add_widget(BoxLayout(size_hint_y=0.1))  # Espaço
        layout.add_widget(self.username)
        layout.add_widget(self.password)
        layout.add_widget(BoxLayout(size_hint_y=0.05))  # Espaço
        layout.add_widget(login_button)
        layout.add_widget(forgot_password)
        layout.add_widget(BoxLayout())  # Espaço flexível
        
        self.add_widget(layout)
    
    def login(self, instance):
        # Simulação de login para o protótipo
        # Em uma implementação real, verificaria as credenciais no banco de dados
        if self.username.text and self.password.text:
            # Determinar o tipo de usuário com base no nome de usuário
            # (simplificação para o protótipo)
            if self.username.text.startswith('prof'):
                self.manager.get_screen('menu').set_user_type('professor')
            elif self.username.text.startswith('pai'):
                self.manager.get_screen('menu').set_user_type('pais')
            elif self.username.text.startswith('dir'):
                self.manager.get_screen('menu').set_user_type('direcao')
            else:
                self.manager.get_screen('menu').set_user_type('secretaria')
            
            self.manager.current = 'menu'
        else:
            # Mostrar mensagem de erro
            self.username.error = True
            self.password.error = True
```

## Menu Principal (menu_screen.py)

```python
from kivymd.uix.screen import MDScreen
from kivymd.uix.button import MDRaisedButton
from kivymd.uix.label import MDLabel
from kivy.uix.boxlayout import BoxLayout
from kivy.metrics import dp

class MenuScreen(MDScreen):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.user_type = None
        self.layout = BoxLayout(orientation='vertical', padding=dp(20), spacing=dp(15))
        
        # Título
        self.title = MDLabel(
            text="Menu Principal",
            halign="center",
            font_style="H5",
            size_hint_y=None,
            height=dp(50)
        )
        
        self.layout.add_widget(self.title)
        self.add_widget(self.layout)
    
    def set_user_type(self, user_type):
        self.user_type = user_type
        self.update_menu()
    
    def update_menu(self):
        # Limpar menu atual
        self.layout.clear_widgets()
        self.layout.add_widget(self.title)
        
        # Criar botões de acordo com o tipo de usuário
        if self.user_type == 'professor':
            self.create_professor_menu()
        elif self.user_type == 'pais':
            self.create_pais_menu()
        elif self.user_type == 'direcao':
            self.create_direcao_menu()
        elif self.user_type == 'secretaria':
            self.create_secretaria_menu()
    
    def create_professor_menu(self):
        buttons = [
            {"text": "Minhas Turmas", "action": self.go_to_turmas},
            {"text": "Registrar Notas", "action": self.go_to_notas},
            {"text": "Registrar Frequência", "action": self.go_to_frequencia},
            {"text": "Ocorrências", "action": self.go_to_ocorrencias},
            {"text": "Comunicados", "action": self.go_to_comunicados},
            {"text": "Calendário", "action": self.go_to_calendario},
            {"text": "Sair", "action": self.logout}
        ]
        self.add_menu_buttons(buttons)
    
    def create_pais_menu(self):
        buttons = [
            {"text": "Boletim", "action": self.go_to_boletim},
            {"text": "Frequência", "action": self.go_to_frequencia},
            {"text": "Ocorrências", "action": self.go_to_ocorrencias},
            {"text": "Comunicados", "action": self.go_to_comunicados},
            {"text": "Calendário", "action": self.go_to_calendario},
            {"text": "Sair", "action": self.logout}
        ]
        self.add_menu_buttons(buttons)
    
    def create_direcao_menu(self):
        buttons = [
            {"text": "Gerenciar Usuários", "action": self.go_to_usuarios},
            {"text": "Aprovar Comunicados", "action": self.go_to_aprovar_comunicados},
            {"text": "Gerenciar Calendário", "action": self.go_to_calendario},
            {"text": "Relatórios", "action": self.go_to_relatorios},
            {"text": "Sair", "action": self.logout}
        ]
        self.add_menu_buttons(buttons)
    
    def create_secretaria_menu(self):
        buttons = [
            {"text": "Gerenciar Alunos", "action": self.go_to_alunos},
            {"text": "Gerenciar Turmas", "action": self.go_to_turmas},
            {"text": "Gerar Relatórios", "action": self.go_to_relatorios},
            {"text": "Enviar Comunicados", "action": self.go_to_comunicados},
            {"text": "Sair", "action": self.logout}
        ]
        self.add_menu_buttons(buttons)
    
    def add_menu_buttons(self, buttons):
        for button in buttons:
            btn = MDRaisedButton(
                text=button["text"],
                size_hint=(1, None),
                height=dp(50),
                on_release=button["action"]
            )
            self.layout.add_widget(btn)
    
    # Funções de navegação
    def go_to_turmas(self, instance):
        # Implementação simplificada para o protótipo
        print("Navegando para Turmas")
    
    def go_to_notas(self, instance):
        self.manager.current = 'notas'
    
    def go_to_frequencia(self, instance):
        self.manager.current = 'frequencia'
    
    def go_to_ocorrencias(self, instance):
        # Implementação simplificada para o protótipo
        print("Navegando para Ocorrências")
    
    def go_to_comunicados(self, instance):
        self.manager.current = 'comunicados'
    
    def go_to_calendario(self, instance):
        # Implementação simplificada para o protótipo
        print("Navegando para Calendário")
    
    def go_to_boletim(self, instance):
        # Implementação simplificada para o protótipo
        print("Navegando para Boletim")
    
    def go_to_usuarios(self, instance):
        # Implementação simplificada para o protótipo
        print("Navegando para Gerenciar Usuários")
    
    def go_to_aprovar_comunicados(self, instance):
        # Implementação simplificada para o protótipo
        print("Navegando para Aprovar Comunicados")
    
    def go_to_relatorios(self, instance):
        # Implementação simplificada para o protótipo
        print("Navegando para Relatórios")
    
    def go_to_alunos(self, instance):
        # Implementação simplificada para o protótipo
        print("Navegando para Gerenciar Alunos")
    
    def logout(self, instance):
        self.manager.current = 'login'
```

## Banco de Dados (db_helper.py)

```python
import sqlite3
import os

# Caminho para o banco de dados
DB_PATH = 'database/escolapp.db'

def init_database():
    """Inicializa o banco de dados com as tabelas necessárias"""
    # Verificar se o diretório existe
    os.makedirs(os.path.dirname(DB_PATH), exist_ok=True)
    
    # Conectar ao banco de dados (cria se não existir)
    conn = sqlite3.connect(DB_PATH)
    cursor = conn.cursor()
    
    # Criar tabelas
    cursor.execute('''
    CREATE TABLE IF NOT EXISTS usuarios (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        nome TEXT NOT NULL,
        login TEXT UNIQUE NOT NULL,
        senha TEXT NOT NULL,
        tipo TEXT NOT NULL,
        email TEXT,
        telefone TEXT,
        sync_status TEXT DEFAULT 'sincronizado',
        last_updated TEXT,
        device_id TEXT
    )
    ''')
    
    cursor.execute('''
    CREATE TABLE IF NOT EXISTS turmas (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        nome TEXT NOT NULL,
        ano TEXT NOT NULL,
        periodo TEXT NOT NULL,
        sync_status TEXT DEFAULT 'sincronizado',
        last_updated TEXT,
        device_id TEXT
    )
    ''')
    
    cursor.execute('''
    CREATE TABLE IF NOT EXISTS alunos (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        usuario_id INTEGER,
        turma_id INTEGER,
        matricula TEXT UNIQUE NOT NULL,
        sync_status TEXT DEFAULT 'sincronizado',
        last_updated TEXT,
        device_id TEXT,
        FOREIGN KEY (usuario_id) REFERENCES usuarios (id),
        FOREIGN KEY (turma_id) REFERENCES turmas (id)
    )
    ''')
    
    cursor.execute('''
    CREATE TABLE IF NOT EXISTS disciplinas (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        nome TEXT NOT NULL,
        descricao TEXT,
        sync_status TEXT DEFAULT 'sincronizado',
        last_updated TEXT,
        device_id TEXT
    )
    ''')
    
    cursor.execute('''
    CREATE TABLE IF NOT EXISTS professores (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        usuario_id INTEGER,
        sync_status TEXT DEFAULT 'sincronizado',
        last_updated TEXT,
        device_id TEXT,
        FOREIGN KEY (usuario_id) REFERENCES usuarios (id)
    )
    ''')
    
    cursor.execute('''
    CREATE TABLE IF NOT EXISTS prof_disc (
        professor_id INTEGER,
        disciplina_id INTEGER,
        turma_id INTEGER,
        sync_status TEXT DEFAULT 'sincronizado',
        last_updated TEXT,
        device_id TEXT,
        PRIMARY KEY (professor_id, disciplina_id, turma_id),
        FOREIGN KEY (professor_id) REFERENCES professores (id),
        FOREIGN KEY (disciplina_id) REFERENCES disciplinas (id),
        FOREIGN KEY (turma_id) REFERENCES turmas (id)
    )
    ''')
    
    cursor.execute('''
    CREATE TABLE IF NOT EXISTS notas (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        aluno_id INTEGER,
        disciplina_id INTEGER,
        bimestre INTEGER,
        valor REAL,
        sync_status TEXT DEFAULT 'sincronizado',
        last_updated TEXT,
        device_id TEXT,
        FOREIGN KEY (aluno_id) REFERENCES alunos (id),
        FOREIGN KEY (disciplina_id) REFERENCES disciplinas (id)
    )
    ''')
    
    cursor.execute('''
    CREATE TABLE IF NOT EXISTS frequencia (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        aluno_id INTEGER,
        disciplina_id INTEGER,
        data TEXT,
        presente BOOLEAN,
        sync_status TEXT DEFAULT 'sincronizado',
        last_updated TEXT,
        device_id TEXT,
        FOREIGN KEY (aluno_id) REFERENCES alunos (id),
        FOREIGN KEY (disciplina_id) REFERENCES disciplinas (id)
    )
    ''')
    
    cursor.execute('''
    CREATE TABLE IF NOT EXISTS comunicados (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        titulo TEXT NOT NULL,
        conteudo TEXT NOT NULL,
        data TEXT NOT NULL,
        autor_id INTEGER,
        aprovado BOOLEAN DEFAULT 0,
        turma_id INTEGER,
        sync_status TEXT DEFAULT 'sincronizado',
        last_updated TEXT,
        device_id TEXT,
        FOREIGN KEY (autor_id) REFERENCES usuarios (id),
        FOREIGN KEY (turma_id) REFERENCES turmas (id)
    )
    ''')
    
    # Inserir dados de exemplo para o protótipo
    insert_sample_data(cursor)
    
    # Commit e fechar conexão
    conn.commit()
    conn.close()

def insert_sample_data(cursor):
    """Insere dados de exemplo para o protótipo"""
    # Verificar se já existem dados
    cursor.execute("SELECT COUNT(*) FROM usuarios")
    if cursor.fetchone()[0] > 0:
        return  # Já existem dados, não inserir novamente
    
    # Inserir usuários de exemplo
    usuarios = [
        ('João Silva', 'dir
(Content truncated due to size limit. Use line ranges to read in chunks)