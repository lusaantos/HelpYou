# HelpYou – Plataforma de Estudos

## Sobre o projeto

O **HelpYou** é uma plataforma gratuita de estudos desenvolvida com o objetivo de auxiliar estudantes na preparação para vestibulares e outros processos seletivos.

A plataforma oferece conteúdos organizados por disciplinas, permitindo que os usuários tenham uma rotina de estudos mais organizada, acompanhem seu progresso e desenvolvam seus conhecimentos de maneira prática e acessível.

O projeto foi desenvolvido como Trabalho de Conclusão de Curso (TCC) da turma **3° IPIA**.

## Objetivos

- Oferecer acesso gratuito a conteúdos educacionais.
- Facilitar a organização da rotina de estudos.
- Auxiliar na preparação para vestibulares.
- Permitir o acompanhamento do desempenho dos estudantes.
- Incentivar a autonomia e a organização durante os estudos.

## Funcionalidades

- **Cadastro e login:** criação de contas e acesso à plataforma.
- **Matérias e conteúdos:** materiais de estudo organizados por disciplinas.
- **Cronograma:** planejamento e organização dos estudos.
- **Desempenho:** acompanhamento das aulas concluídas.
- **Perfil:** visualização e edição de informações pessoais.
- **Contato:** formulário para envio de mensagens à equipe.

## Tecnologias utilizadas

### Front-end
- HTML5
- CSS3
- JavaScript
- Bootstrap

### Back-end
- Node.js
- Express

### Banco de dados e serviços
- Supabase

## Estrutura do projeto

O projeto está organizado em pastas para facilitar a manutenção e o desenvolvimento:

- `css/` – arquivos de estilização.
- `js/` – scripts JavaScript.
- `img/` – imagens e elementos visuais.
- `fontes/` – arquivos de fontes utilizadas.
- `pages/` – páginas da plataforma.
- `server/` – arquivos responsáveis pelo back-end.
- `package.json` – dependências e configurações do projeto.

## Como executar o projeto

### 1. Pré-requisitos

Antes de iniciar, é necessário ter instalado:

- [Node.js](https://nodejs.org/)
- [Visual Studio Code](https://code.visualstudio.com/)
- Um navegador de internet.

### 2. Instalação das dependências

Abra a pasta principal do projeto no VS Code e execute no terminal:

```bash
npm install
```

Esse comando instala as dependências registradas no `package.json`.

### 3. Configuração do ambiente

Configure o arquivo `.env` na pasta principal do projeto com as credenciais do Supabase:

```env
SUPABASE_URL=sua_url_do_supabase
SUPABASE_KEY=sua_chave_do_supabase
FRONTEND_URL=http://127.0.0.1:5500
```

Não compartilhe suas chaves privadas nem envie o arquivo `.env` para repositórios públicos.

### 4. Inicialização do servidor

Execute no terminal:

```bash
npm run dev
```

O servidor será iniciado na porta 3000:

```text
http://localhost:3000
```

### 5. Acesso à plataforma

Abra o arquivo inicial do projeto utilizando o Live Server do VS Code ou o servidor configurado para o front-end.

## Banco de dados

O HelpYou utiliza o **Supabase** para armazenar e gerenciar informações dos usuários, dados de perfil, desempenho e mensagens enviadas pelo formulário de contato.

## Desenvolvedores

Projeto desenvolvido como Trabalho de Conclusão de Curso pela turma **3° IPIA**.

## Licença

Projeto desenvolvido para fins educacionais.
