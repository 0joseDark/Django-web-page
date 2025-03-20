# Django web page
O **Django** é um framework web de alto nível para **Python** que permite o desenvolvimento rápido e seguro de aplicações web. Ele é utilizado para criar sites dinâmicos, APIs e sistemas complexos, como redes sociais, plataformas de e-commerce e sistemas de gerenciamento de conteúdo.

### 📌 **Principais características do Django:**
- **Rápido desenvolvimento**: Segue o princípio **"DRY" (Don't Repeat Yourself)**, reduzindo a repetição de código.
- **Arquitetura MVC (Model-View-Controller)**: Facilita a organização do código.
- **ORM (Object-Relational Mapping)**: Permite interagir com bases de dados como MySQL, PostgreSQL e SQLite sem escrever SQL diretamente.
- **Segurança integrada**: Protege contra ataques como SQL Injection, Cross-Site Scripting (XSS) e Cross-Site Request Forgery (CSRF).
- **Administração automática**: Gera automaticamente um painel administrativo para gerenciar usuários e conteúdos.

### 🛠 **Como instalar o Django no Windows 10?**
1. **Abrir o Prompt de Comando** (CMD) ou PowerShell.
2. **Instalar com o pip**:
   ```bash
   pip install django
   ```
3. **Verificar a instalação**:
   ```bash
   django-admin --version
   ```
4. **Criar um novo projeto**:
   ```bash
   django-admin startproject meu_projeto
   ```
5. **Executar o servidor de desenvolvimento**:
   ```bash
   cd meu_projeto
   python manage.py runserver
   ```
   Acesse **http://127.0.0.1:8000/** no navegador para ver o Django funcionando!
---
- Django é ideal para projetos web robustos e escaláveis, facilitando o desenvolvimento de aplicações completas com pouco esforço.
Aqui está um exemplo de um projeto Django básico com uma página HTML.  
---
## **📌 Estrutura do Projeto**
```
meu_projeto/
│── meu_projeto/
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│── app/
│   ├── templates/
│   │   ├── index.html
│   ├── views.py
│   ├── urls.py
│── manage.py
```

---

## **1️⃣ Criar o Projeto Django**
```bash
django-admin startproject meu_projeto
cd meu_projeto
python manage.py startapp app
```

---

## **2️⃣ Configurar `settings.py`**
Edite `meu_projeto/settings.py` e adicione a aplicação ao projeto:
```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'app',  # Adicione esta linha
]
```

---

## **3️⃣ Criar a `views.py`**
Edite `app/views.py`:
```python
from django.shortcuts import render

def home(request):
    return render(request, 'index.html')
```

---

## **4️⃣ Criar o `urls.py` da aplicação**
Edite `app/urls.py`:
```python
from django.urls import path
from .views import home

urlpatterns = [
    path('', home, name='home'),
]
```

---

## **5️⃣ Configurar o `urls.py` do projeto**
Edite `meu_projeto/urls.py`:
```python
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('app.urls')),  # Inclui as rotas da app
]
```

---

## **6️⃣ Criar a Página HTML**
Crie a pasta `app/templates/` e dentro dela, crie `index.html`:
```html
<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página Django</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; padding: 50px; }
        h1 { color: #007bff; }
    </style>
</head>
<body>
    <h1>Bem-vindo ao Django!</h1>
    <p>Esta é uma página HTML servida pelo Django.</p>
</body>
</html>
```

---

## **7️⃣ Executar o Servidor**
```bash
python manage.py runserver
```
Agora, acesse **http://127.0.0.1:8000/** e verá a página Django funcionando!
