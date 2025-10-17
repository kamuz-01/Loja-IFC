# Loja IFC 🛒

Protótipo de e-commerce desenvolvida em Django como projeto prático para o Instituto Federal Catarinense - Campus Fraiburgo. O sistema desenvolvido contém como funcionalidades implementadas o gerenciamento de produtos, carrinho de compras e autenticação de usuários.

## 📋 Sobre o Projeto

A Loja IFC é um protótipo de comércio eletrônico, desenvolvido com Django e Bootstrap, que permite que usuários simulem a busca, filtragem e compra de produtos de forma intuitiva. O projeto foi desenvolvido como material de aprendizado e demonstração de boas práticas em desenvolvimento web com Python.

**Plataforma em produção**: [kamuz01.pythonanywhere.com](https://kamuz01.pythonanywhere.com)

## ✨ Funcionalidades Principais

- 🛍️ Catálogo de produtos com busca e filtros avançados
- 🛒 Carrinho de compras com gerenciamento de quantidades
- 👤 Sistema de autenticação de usuários
- 📝 Cadastro de novos usuários
- 🏠 Página sobre a loja
- 📧 Formulário de contato
- 📱 Interface responsiva e moderna com Bootstrap
- 🔍 Filtros por nome, preço e disponibilidade

## 🛠️ Tecnologias Utilizadas

| Categoria | Tecnologia |
|-----------|-----------|
| **Backend** | Django 5.x, Python 3.x |
| **Frontend** | HTML5, CSS3, Bootstrap 5 |
| **Banco de Dados** | SQLite |
| **ORM** | Django ORM |
| **Filtros** | django-filters |
| **Icons** | Font Awesome 6 |
| **Formulários** | django-widget-tweaks |

## 📦 Requisitos do Sistema

- Python 3.8 ou superior
- pip (gerenciador de pacotes Python)
- Git
- Virtualenv (recomendado)

## 🚀 Instalação e Configuração

### 1. Clone o repositório

```bash
git clone https://github.com/kamuz-01/Loja-IFC.git
cd Loja-IFC
```

### 2. Crie e ative um ambiente virtual

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Configure as variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto (opcional, para desenvolvimento):

```env
DEBUG=True
SECRET_KEY=sua-chave-secreta-aqui
ALLOWED_HOSTS=localhost,127.0.0.1
DATABASE_URL=sqlite:///db.sqlite3
```

### 5. Execute as migrações do banco de dados

```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Crie um usuário administrador

```bash
python manage.py createsuperuser
```

Digite as informações solicitadas (username, email, senha).

### 7. Execute o servidor de desenvolvimento

```bash
python manage.py runserver
```

Acesse a aplicação em `http://localhost:8000` 🎉

## 📂 Estrutura do Projeto

```
Loja-IFC/
├── manage.py                      # Gerenciador de comandos Django
├── requirements.txt               # Dependências do projeto
├── db.sqlite3                     # Banco de dados (desenvolvimento)
│
├── core/                          # Configurações principais do projeto
│   ├── settings.py               # Configurações do Django
│   ├── urls.py                   # URLs principais
│   ├── wsgi.py                   # Aplicação WSGI
│   └── asgi.py                   # Aplicação ASGI
│
├── loja/                          # App principal - Produtos
│   ├── models.py                 # Modelo Produto
│   ├── views.py                  # Views (CBV e FBV)
│   ├── urls.py                   # URLs da app loja
│   ├── filters.py                # Filtros de produtos
│   ├── admin.py                  # Admin do Django
│   └── migrations/               # Migrações do banco
│
├── carrinho/                      # App - Carrinho de Compras
│   ├── carrinho.py               # Lógica do carrinho (session)
│   ├── context_processor.py      # Processador de contexto
│   └── migrations/
│
├── conta/                         # App - Autenticação e Conta
│   ├── forms.py                  # Formulário de registro
│   ├── views.py                  # Login, registro, exclusão
│   ├── urls.py                   # URLs da autenticação
│   └── migrations/
│
├── static/                        # Arquivos estáticos
│   └── css/                      # Estilos customizados
│       ├── estilos_base.css
│       ├── contato.css
│       ├── excluir-confirm.css
│       ├── minha-conta.css
│       ├── password-done.css
│       ├── password-form.css
│       ├── produto-detail.css
│       └── sobre.css
│
├── media/                         # Uploads de usuários
│   └── produtos/                 # Imagens de produtos
│
└── templates/                     # Templates HTML
    ├── base.html                 # Template base
    ├── lista_produtos.html
    ├── produto_detail.html
    ├── carrinho.html
    ├── checkout_concluido.html
    ├── registrar.html
    ├── minha_conta.html
    ├── contato.html
    ├── sobre.html
    ├── partials/
    │   └── _card_produto.html   # Componente reutilizável
    └── registration/            # Templates de autenticação
        ├── login.html
        ├── password_change_form.html
        └── password_change_done.html
```

## 📖 Como Usar

### 👤 Como Usuário

1. **Navegar pelos produtos**: Acesse a página inicial para ver o catálogo
2. **Buscar e filtrar**: Use a página "Pesquisar" para filtrar por nome, preço e disponibilidade
3. **Ver detalhes**: Clique em "Ver Detalhes" para informações completas do produto
4. **Registrar-se**: Clique em "Registrar" para criar uma conta
5. **Adicionar ao carrinho**: Após fazer login, adicione produtos ao carrinho
6. **Gerenciar carrinho**: Aumente/diminua quantidades ou remova itens
7. **Finalizar compra**: Clique em "Finalizar compra" para completar a transação

### 🛠️ Como Administrador

1. Acesse `http://localhost:8000/admin`
2. Faça login com suas credenciais de superusuário
3. **Gerenciar Produtos**:
   - Adicione novos produtos
   - Edite preço, nome, disponibilidade e imagem
   - A disponibilidade atualiza automaticamente baseada no estoque

### 📱 Responsividade

A aplicação é totalmente responsiva e funciona perfeitamente em:
- Desktop
- Tablets
- Smartphones

## 🔒 Segurança

- ✅ Proteção CSRF integrada
- ✅ Senhas hasheadas com algoritmo seguro
- ✅ Autenticação obrigatória para carrinho e checkout
- ✅ Validação de estoque antes do checkout
- ✅ Validação de formulários no lado do servidor

## 🚀 Deploy no PythonAnywhere

O projeto está configurado para produção no PythonAnywhere. Se desejar fazer deploy:

1. Configure as variáveis de ambiente em produção
2. Colete arquivos estáticos:
   ```bash
   python manage.py collectstatic --noinput
   ```
3. Configure o arquivo WSGI no PythonAnywhere
4. Mapeie os arquivos estáticos e de mídia

## 📝 Modelos de Dados

### Produto
```
- id (PK)
- nome (CharField)
- preco (DecimalField)
- disponivel (BooleanField)
- imagem (ImageField)
- quantidade (IntegerField)
```

**Lógica especial**: A disponibilidade se atualiza automaticamente. Se quantidade ≤ 0, o produto fica indisponível.

### Carrinho (Session-based)
Armazenado na sessão do usuário com estrutura:
```python
{
    'produto_id': {
        'quantidade': int,
        'preco': str
    }
}
```

## 🐛 Troubleshooting

### Erro: `ModuleNotFoundError: No module named 'django'`

Verifique se o ambiente virtual está ativado e instale as dependências:
```bash
pip install -r requirements.txt
```

### Erro: `django.db.utils.OperationalError: no such table`

Execute as migrações:
```bash
python manage.py migrate
```

### Imagens não aparecem em produção

Execute o comando para coletar arquivos estáticos:
```bash
python manage.py collectstatic --noinput
```

### Erro de permissão na pasta `media/`

Verifique permissões:
```bash
chmod 755 media/
```

## 🔄 Fluxo de Checkout

```
1. Usuário autentica ✓
2. Adiciona produtos ao carrinho ✓
3. Revisa carrinho (pode modificar quantidades) ✓
4. Clica em "Finalizar compra" ✓
5. Sistema valida estoque de cada produto ✓
6. Se OK: decrementa quantidade no BD e limpa carrinho ✓
7. Se ERRO: mostra mensagem e retorna ao carrinho ✓
8. Mostra página de sucesso ✓
```

## 📚 Recursos Adicionais

- [Documentação Django](https://docs.djangoproject.com/)
- [Bootstrap 5](https://getbootstrap.com/)
- [django-filters](https://django-filter.readthedocs.io/)
- [Font Awesome Icons](https://fontawesome.com/icons)

## 🤝 Contribuição

Contribuições são bem-vindas! Para contribuir:

1. Faça um Fork do projeto
2. Crie uma Branch para sua feature (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'Add some MinhaFeature'`)
4. Push para a Branch (`git push origin feature/MinhaFeature`)
5. Abra um Pull Request

## 📜 Licença

Este projeto está licenciado sob a **MIT License**. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👤 Desenvolvedor

**Karli De Jesus Munoz Manzano**

📧 **Email**: karli.manzano@estudantes.ifc.edu.br

🎓 **Instituição**: Instituto Federal Catarinense - Campus Fraiburgo

## 📞 Suporte

Para dúvidas ou sugestões sobre o projeto, entre em contato através do formulário de contato na aplicação ou envie um email para o desenvolvedor.

---

*Desenvolvido com ❤️ para a comunidade de desenvolvimento do IFC - Fraiburgo*

**Todos os direitos reservados © 2025**