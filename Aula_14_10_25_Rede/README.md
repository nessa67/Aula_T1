# Rack Management

Sistema simples para gerenciar conexões de Rack usando Flask e MySQL.

## Pré-requisitos

- Python 3.13 ou superior
- [XAMPP](https://www.apachefriends.org/pt_br/index.html) (MySQL/MariaDB e phpMyAdmin)
- [uv](https://github.com/astral-sh/uv) (gerenciador de pacotes Python rápido)

## Instalação

**UV instalação:**
   ```sh
    <!-- instala o uv na maquina: -->
        winget install astral-sh.uv
    <!-- inicia o uv na pasta: -->
        uv init --bare ------> no terminal powershel
    <!-- inicia o ambiente virtual: -->
        uv venv
    <!-- chama o vs -->
        code .
    <!-- adiciona os pacotes: -->
        uv add nome_da_api
    <!-- mostra as pacotes instalados: -->
        uv tree
    <!-- desativar o ambiente virtual: -->
        deactivate
```

1.1 **Clone o repositório:**
   ```sh
   git clone https://github.com/marckcm/Rede_a1.git   
   ```

2. **Instale as dependências com uv:**
   ```sh
   no terminal do PowerShell
   uv add flask mysql-connector-python
   ```

3. **Instale e configure o XAMPP:**
   - Baixe e instale o XAMPP.
   - Inicie o Apache e o MySQL pelo painel do XAMPP.

4. **Crie o banco de dados usando o phpMyAdmin:**
   - Acesse [http://localhost/phpmyadmin](http://localhost/phpmyadmin) no navegador.
   - Execute os comandos SQL abaixo para criar o banco e a tabela:

     ```sql
     -- Verificar se o banco de dados já existe e criar se não existir
     CREATE DATABASE IF NOT EXISTS rack_management;

     -- Usar o banco de dados rack_management
     USE rack_management;

     -- Verificar se a tabela connections já existe e criar se não existir
     CREATE TABLE IF NOT EXISTS connections (
         id INT AUTO_INCREMENT PRIMARY KEY,
         switch_port VARCHAR(50) NOT NULL,
         patch_panel_port VARCHAR(50) NOT NULL
     );
     ```

## Utilização

1. **Execute o servidor Flask:**
   ```sh
   uv venv   
   uv run python app.py
   ```

2. **Acesse no navegador:**
   ```
   http://localhost:5000
   ```

## Estrutura do Projeto

- `app.py` — Código principal Flask
- `pyproject.toml` — Dependências do projeto
- `static/style.css` — Estilos CSS
- `templates/` — Templates HTML

## Licença

MIT