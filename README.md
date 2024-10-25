# Documentação do Projeto Django

## Introdução

Este projeto foi criado com o objetivo de demonstrar como configurar e desenvolver um projeto básico utilizando o Django. Nele, abordaremos desde a instalação do Django até a criação de uma estrutura inicial de projeto, configurando URLs, views, e modelos. O foco é fornecer um exemplo prático para iniciantes.

## Instalação do Django

1. Abra o terminal (CMD, PowerShell, ou terminal de sua preferência).
2. Execute o seguinte comando para instalar o Django:

   ```bash
   pip install django
   ```

## Criando um Projeto Django

1. **Crie um novo projeto**:

   ```bash
   django-admin startproject nome_do_projeto
   ```

   Substitua `nome_do_projeto` pelo nome que você deseja para o seu projeto.

2. **Navegue para o diretório do projeto**:

   ```bash
   cd nome_do_projeto
   ```

## Estrutura Inicial do Projeto

Após criar o projeto, você verá a seguinte estrutura de diretórios:

```
nome_do_projeto/
    ├── manage.py
    └── nome_do_projeto/
        ├── __init__.py
        ├── settings.py
        ├── urls.py
        └── wsgi.py
```

- **manage.py**: Utilitário de linha de comando para interagir com o projeto.
- **settings.py**: Arquivo de configuração do projeto.
- **urls.py**: Configuração de URLs do projeto.
- **wsgi.py**: Interface para servidores WSGI.

## Executando o Servidor Local

Para executar o servidor de desenvolvimento e visualizar seu projeto no navegador, execute o seguinte comando:

```bash
python manage.py runserver
```

Acesse a página inicial padrão do Django em [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

## Criando um Aplicativo Django

Em Django, a funcionalidade é organizada em aplicativos. Para criar um aplicativo, execute:

```bash
python manage.py startapp nome_do_app
```

Substitua `nome_do_app` pelo nome desejado para o seu aplicativo.

### Registrando o App no Projeto

1. Abra o arquivo `settings.py` do seu projeto (localizado em `nome_do_projeto/nome_do_projeto/settings.py`).
2. Adicione o nome do seu app à lista `INSTALLED_APPS`:

   ```python
   INSTALLED_APPS = [
       ...,
       'nome_do_app',
   ]
   ```

## Configurando URLs

1. Abra o arquivo `urls.py` do seu projeto (localizado em `nome_do_projeto/nome_do_projeto/urls.py`).
2. Importe as views do seu app e configure as URLs:

   ```python
   from django.contrib import admin
   from django.urls import path, include
   from nome_do_app import views

   urlpatterns = [
       path('', views.home, name='home'),
       path('admin/', admin.site.urls),
   ]
   ```

## Criando Views

1. Abra o arquivo `views.py` do seu app (localizado em `nome_do_projeto/nome_do_app/views.py`).
2. Crie uma view básica:

   ```python
   from django.http import HttpResponse

   def home(request):
       return HttpResponse("Bem-vindo ao projeto Django!")
   ```

## Executando o Projeto

Após todas as configurações, execute novamente o servidor local:

```bash
python manage.py runserver
```

Acesse [http://127.0.0.1:8000/](http://127.0.0.1:8000/) para ver sua aplicação em funcionamento.

## Considerações Finais

Este projeto é um exemplo básico de como iniciar um projeto Django. Ele foi criado para demonstrar a instalação, configuração de um projeto e criação de um aplicativo. Para expandir este projeto, você pode explorar mais sobre modelos, formulários, autenticação de usuários e outros recursos do Django.

## Recursos Adicionais

- [Documentação Oficial do Django](https://docs.djangoproject.com/en/stable/)
- [Tutorial de Django](https://docs.djangoproject.com/en/stable/intro/tutorial01/)
