# Guia para Hospedar o Site EscolApp no GitHub Pages

Este documento contém instruções detalhadas para hospedar o site do projeto EscolApp no GitHub Pages.

## Estrutura do Site

O site do EscolApp tem uma estrutura simples:
- `index.html` - Página principal do site
- `docs/` - Pasta contendo as páginas de documentação

## Passos para Hospedagem no GitHub Pages

### 1. Criar uma conta no GitHub
- Acesse [github.com](https://github.com)
- Clique em "Sign up" (Cadastrar-se)
- Preencha seu e-mail, crie uma senha e escolha um nome de usuário
- Siga as instruções para verificar sua conta

### 2. Criar um novo repositório
- Após fazer login, clique no ícone "+" no canto superior direito
- Selecione "New repository" (Novo repositório)
- Nomeie o repositório como "escolapp" ou "projeto-escolapp"
- Mantenha a opção "Public" (Público) selecionada
- Marque a opção "Add a README file" (Adicionar um arquivo README)
- Clique em "Create repository" (Criar repositório)

### 3. Fazer upload dos arquivos do site
- No seu repositório, clique em "Add file" > "Upload files"
- Arraste todos os arquivos da pasta `/home/ubuntu/escolapp_site/` para a área de upload
- Certifique-se de incluir o arquivo `index.html` e a pasta `docs/`
- Role para baixo e clique em "Commit changes" (Confirmar alterações)

### 4. Configurar o GitHub Pages
- No seu repositório, clique na aba "Settings" (Configurações)
- Role até encontrar a seção "GitHub Pages" (ou clique em "Pages" no menu lateral)
- Em "Source", selecione "main" (ou "master") no menu dropdown
- Clique em "Save" (Salvar)
- Aguarde alguns minutos para o site ficar disponível
- O URL do seu site será: `https://seunomedeusuario.github.io/escolapp/`

### 5. Verificar seu site
- Acesse o URL fornecido pelo GitHub Pages
- Verifique se todas as páginas e links funcionam corretamente

## Dicas Adicionais

- Se encontrar problemas com links quebrados, pode ser necessário ajustar os caminhos nos arquivos HTML
- Para atualizar o site, basta fazer upload de novos arquivos ou editar os existentes
- O GitHub mantém um histórico de todas as alterações
- Você pode personalizar o domínio nas configurações do GitHub Pages (requer um domínio próprio)

## Suporte

Se precisar de ajuda adicional, consulte a [documentação oficial do GitHub Pages](https://docs.github.com/pt/pages).
