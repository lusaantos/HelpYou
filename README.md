# HelpYou – Plataforma de Estudos

## 1. Sobre o projeto

O **HelpYou** é uma plataforma gratuita de estudos desenvolvida com o objetivo de auxiliar estudantes na preparação para vestibulares e outros processos seletivos.

A plataforma oferece conteúdos organizados por disciplinas, permitindo que os usuários organizem sua rotina de estudos, acompanhem seu progresso e desenvolvam seus conhecimentos de maneira prática e acessível.

O projeto foi desenvolvido como Trabalho de Conclusão de Curso (TCC) por alunas do curso Técnico de Informática para a Internet.

## 2. Objetivos

- Oferecer acesso gratuito a conteúdos educacionais.
- Facilitar a organização da rotina de estudos.
- Auxiliar na preparação para vestibulares.
- Permitir o acompanhamento do desempenho dos estudantes.
- Incentivar a autonomia e a organização durante os estudos.

## 3. Funcionalidades

- **Cadastro e login:** criação de contas e acesso à plataforma.
- **Matérias e conteúdos:** materiais de estudo organizados por disciplinas.
- **Cronograma:** planejamento e organização dos estudos.
- **Desempenho:** acompanhamento das aulas concluídas e do progresso.
- **Perfil:** visualização e edição de informações pessoais.
- **Contato:** formulário para envio de mensagens à equipe.

## 4. Tecnologias utilizadas

### Front-end
- HTML5
- CSS3
- JavaScript
- Bootstrap

### Back-end
- Node.js
- Express

### Banco de dados e serviços
- Supabase (PostgreSQL e autenticação).

## 5. Estrutura do projeto

O projeto está organizado em pastas para facilitar a manutenção e o desenvolvimento:

- `css/` – arquivos de estilização.
- `js/` – scripts JavaScript.
- `img/` – imagens e elementos visuais.
- `fontes/` – arquivos de fontes utilizadas.
- `pages/` – páginas da plataforma.
- `server/` – arquivos responsáveis pelo back-end.
- `package.json` – dependências e configurações do projeto.

## 6. Como executar o projeto

### 6.1. Pré-requisitos

Antes de iniciar, é necessário ter instalado:

- [Node.js](https://nodejs.org/) – versão 24.15.0 ou compatível.
- [Visual Studio Code](https://code.visualstudio.com/).
- Um navegador de internet.

### 6.2. Instalação das dependências

Abra a pasta principal do projeto no Visual Studio Code e execute no terminal:

```bash
npm install
```

Esse comando instala as dependências registradas no arquivo `package.json`.

### 6.3. Configuração do ambiente

Crie um arquivo chamado `.env` na pasta principal do projeto e configure as credenciais de acesso ao Supabase:

```env
SUPABASE_URL=sua_url_do_supabase
SUPABASE_KEY=sua_chave_do_supabase
FRONTEND_URL=http://127.0.0.1:5500
```

Substitua os valores de exemplo pelas credenciais correspondentes ao projeto Supabase.

O arquivo `.env` deve permanecer local e não deve ser compartilhado na entrega.

### 6.4. Inicialização do servidor

No terminal do Visual Studio Code, execute:

```bash
npm run dev
```

O servidor será iniciado na porta 3000, podendo ser acessado pelo endereço:

```text
http://localhost:3000
```

### 6.5. Acesso à plataforma

Após iniciar o servidor back-end, abra o arquivo inicial do projeto no navegador para acessar a plataforma.

## 7. Banco de dados

O HelpYou utiliza o **Supabase** como serviço de banco de dados PostgreSQL e autenticação.

A ferramenta é responsável por armazenar e gerenciar informações complementares dos perfis dos usuários, registros de estudo e mensagens enviadas pelo formulário de contato.

### 7.1. Estrutura do banco de dados

No schema `public`, foram identificadas as seguintes tabelas:

- `mensagens_contato`: armazena nome, e-mail, assunto, mensagem, situação de leitura e data de criação.
- `perfis`: armazena informações complementares do perfil do usuário.
- `registros_estudo`: registra matéria, tempo de estudo, usuário relacionado e data de criação.

### 7.2. Relacionamentos

- `perfis.id` referencia `auth.users.id`, com exclusão em cascata (`ON DELETE CASCADE`).
- `registros_estudo.usuario_id` referencia `auth.users.id`, também com exclusão em cascata (`ON DELETE CASCADE`).

As tabelas `perfis` e `registros_estudo` estão relacionadas ao sistema de autenticação do Supabase.

### 7.3. Configuração do banco de dados

Para reproduzir a estrutura disponibilizada:

1. Crie um projeto no [Supabase](https://supabase.com/).
2. Acesse o **SQL Editor** do projeto.
3. Abra o arquivo `bancoDados_helpyou.sql`, disponibilizado junto ao projeto.
4. Copie o conteúdo do arquivo e execute no SQL Editor.
5. Configure as variáveis de ambiente do back-end conforme a seção 6.3 deste documento.

### 7.4. Observações sobre a exportação

O arquivo SQL foi elaborado com base nas colunas, tipos, valores padrão, chaves primárias e chaves estrangeiras consultadas no painel do Supabase.

É importante destacar que esse arquivo não corresponde a um dump integral do banco de dados original.

As políticas de Row Level Security (RLS), triggers, índices adicionais e restrições `CHECK` não foram exportados nem conferidos. Portanto, esses elementos devem ser verificados separadamente no painel do Supabase caso seja necessária uma reprodução integral do ambiente original.

## 8. Segurança

As credenciais de acesso ao Supabase devem ser mantidas em um arquivo `.env` local.

Não compartilhe senhas, tokens, chaves privadas, a chave `service_role` ou dados pessoais dos usuários.

O arquivo `.env` com credenciais reais não deve ser incluído na entrega do projeto.

## 9. Desenvolvedores

Projeto desenvolvido como Trabalho de Conclusão de Curso por alunas do **3° IPIA**.

## 10. Licença

Projeto desenvolvido para fins educacionais.

Atenção antes de enviar: confira se o arquivo SQL realmente contém a estrutura descrita na documentação e se o orientador terá acesso às credenciais necessárias para testar o sistema. A chave `service_role` e outras credenciais administrativas nunca devem ser incluídas no ZIP.
