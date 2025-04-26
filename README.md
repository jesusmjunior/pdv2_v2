# PDV-2028 - Sistema de Ponto de Venda Atualizado

Sistema de Ponto de Venda (PDV) desenvolvido com JavaScript para front-end e Node.js/Express com PostgreSQL para back-end. Versão 2.0 com melhorias de desempenho e correções de compatibilidade.

## Funcionalidades

- Autenticação de usuários
- Dashboard com indicadores
- Gestão de produtos
- Gestão de estoque
- Gestão de clientes
- Registro e controle de vendas
- Geração de recibos
- Relatórios

## Tecnologias Utilizadas

- **Front-end:** HTML5, CSS3, JavaScript Vanilla
- **Back-end:** Node.js, Express
- **Banco de Dados:** PostgreSQL
- **Autenticação:** JWT (JSON Web Tokens)
- **Hospedagem:** Render.com

## Novidades na Versão 2.0

- Migração de bcrypt para bcryptjs para melhor compatibilidade
- Otimização do processo de build no Render
- Correção de avisos de pacotes depreciados
- Simplificação da configuração de deploy
- Adição de .npmrc para supressão de avisos de funding
- Configuração padronizada para usar apenas npm (sem yarn)

## Estrutura do Projeto

```
/
├── api/                 # API Node.js/Express
│   ├── controllers/     # Controladores da API
│   ├── models/          # Modelos de dados
│   └── index.js         # Ponto de entrada da API
├── scripts/             # Scripts utilitários
│   └── setup-db.js      # Script para inicialização do banco de dados
├── src/                 # Aplicação front-end
│   ├── css/             # Estilos CSS
│   ├── js/              # JavaScript
│   │   ├── components/  # Componentes reutilizáveis
│   │   ├── core/        # Funções principais
│   │   └── modules/     # Módulos específicos
│   └── pages/           # Páginas HTML
├── .npmrc               # Configuração do npm
├── .gitignore           # Arquivos ignorados pelo git
├── package.json         # Dependências e scripts
└── render.yaml          # Configuração de deploy na Render
```

## Instruções para Desenvolvimento Local

1. Clone o repositório:
   ```bash
   git clone https://github.com/jesusmjunior/pdv-2028.git
   cd pdv-2028
   ```

2. Instale as dependências:
   ```bash
   npm install
   ```

3. Crie um arquivo `.env` com as configurações do banco de dados:
   ```
   DB_HOST=localhost
   DB_USER=seu_usuario
   DB_PASSWORD=sua_senha
   DB_NAME=pdv_2028
   DB_PORT=5432
   JWT_SECRET=sua_chave_secreta
   ```

4. Inicialize o banco de dados:
   ```bash
   npm run setup-db
   ```

5. Inicie o servidor de desenvolvimento:
   ```bash
   npm run dev
   ```

6. Acesse a aplicação em [http://localhost:3000](http://localhost:3000)

### Credenciais padrão:
- **Usuário:** admin
- **Senha:** admin

## Deploy no Render.com

O projeto está configurado para deploy automático na Render.com usando o arquivo `render.yaml`. O deploy está otimizado para evitar conflitos e avisos.

Site: [https://pdv-2028.onrender.com](https://pdv-2028.onrender.com)

## Instruções para Atualizar o Repositório

1. Clone o repositório original:
   ```bash
   git clone https://github.com/jesusmjunior/pdv-2028.git
   ```

2. Crie uma nova branch para v2:
   ```bash
   git checkout -b v2
   ```

3. Remova o package-lock.json:
   ```bash
   rm package-lock.json
   ```

4. Substitua bcrypt por bcryptjs:
   ```bash
   npm remove bcrypt
   npm install bcryptjs
   ```

5. Copie os arquivos atualizados e envie para o GitHub:
   ```bash
   git add .
   git commit -m "Atualização para versão 2.0 com bcryptjs e correções de deploy"
   git push -u origin v2
   ```

6. Faça um merge para a main:
   ```bash
   git checkout main
   git merge v2
   git push
   ```

7. No Render, atualize a configuração de build conforme o render.yaml atualizado.