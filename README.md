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

Na pasta principal do projeto (a mesma em que está o `package.json`), crie uma cópia do arquivo `.env.example` e renomeie essa cópia para `.env`. Preencha as variáveis conforme as orientações abaixo:

```env
SUPABASE_URL=https://SEU-PROJETO.supabase.co
SUPABASE_KEY=SUA_CHAVE_PUBLICAVEL_DO_SUPABASE
FRONTEND_URL=http://127.0.0.1:5500
GMAIL_USER=seu_email@gmail.com
GMAIL_TO=email_que_recebera_as_mensagens@gmail.com
GMAIL_APP_PASSWORD=SUA_SENHA_DE_APLICATIVO
```

- `SUPABASE_URL`: URL do projeto Supabase.
- `SUPABASE_KEY`: chave pública do projeto (publishable key ou anon key, conforme a configuração disponível no painel). Não utilize a chave `service_role` ou outra chave secreta em código acessível pelo navegador.
- `FRONTEND_URL`: endereço usado pelo front-end durante o desenvolvimento. Ajuste-o caso a porta ou o endereço do Live Server seja diferente.
- `GMAIL_USER`: conta Gmail utilizada pelo Nodemailer para enviar mensagens.
- `GMAIL_TO`: endereço que receberá as mensagens do formulário de contato.
- `GMAIL_APP_PASSWORD`: senha de aplicativo do Gmail, quando o envio de e-mails estiver configurado para essa conta.

Para localizar os dados do Supabase, entre no painel do projeto e abra as configurações/API do projeto (ou a área de conexão/API, conforme a versão do painel). Copie a URL do projeto para `SUPABASE_URL` e a chave pública para `SUPABASE_KEY`.

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

### 7.3. Como conectar o projeto ao Supabase

A conexão é feita pelo back-end Node.js usando a biblioteca `@supabase/supabase-js`. O servidor lê `SUPABASE_URL` e `SUPABASE_KEY` do arquivo `.env` e utiliza esses valores para criar o cliente Supabase.

Siga os passos:

1. Acesse [supabase.com](https://supabase.com/) e entre na sua conta.
2. Crie um projeto ou abra o projeto Supabase que será utilizado pelo HelpYou. Guarde a senha do banco em local seguro; ela não é a mesma coisa que a chave pública da API.
3. No painel do projeto, localize a URL do projeto e a chave pública da API (publishable key ou anon key, conforme a configuração apresentada). Copie a URL para `SUPABASE_URL` e a chave pública para `SUPABASE_KEY` no arquivo `.env`.
4. No painel do Supabase, abra o **SQL Editor** e crie uma nova consulta.
5. Abra o arquivo `bancoDados_helpyou.sql` que acompanha a entrega, copie todo o conteúdo e cole na consulta do SQL Editor.
6. Execute o script. Ele cria as tabelas `mensagens_contato`, `perfis` e `registros_estudo` no schema `public`. Confira no **Table Editor** se as três tabelas foram criadas.
7. Volte ao projeto no VS Code e confirme que o `.env` está salvo na pasta principal, junto ao `package.json`, com a URL e a chave corretas.
8. Abra o terminal nessa mesma pasta e execute `npm install` para instalar as dependências.
9. Inicie o servidor com `npm run dev`. O servidor utiliza as variáveis do `.env` para conectar ao Supabase.
10. Abra o front-end pelo endereço configurado em `FRONTEND_URL` (por exemplo, usando o Live Server do VS Code). Faça um teste com uma conta de demonstração e confira as funcionalidades que consultam ou gravam dados.

**Importante sobre as tabelas relacionadas à autenticação:** `perfis.id` e `registros_estudo.usuario_id` fazem referência a `auth.users.id`. Portanto, para testar essas funcionalidades, primeiro crie uma conta pela tela de cadastro do HelpYou ou pelo recurso de autenticação do Supabase. O script SQL não cria usuários de demonstração.

### 7.4. Verificações e solução de problemas

- **URL ou chave incorreta:** confira se não há espaços antes ou depois dos valores no `.env` e se eles pertencem ao mesmo projeto Supabase.
- **Variáveis não reconhecidas:** confirme que o `.env` está na pasta em que o servidor é iniciado e reinicie o servidor depois de alterar o arquivo.
- **Erro ao consultar ou gravar dados:** confira se as tabelas foram criadas no schema `public` e se as políticas de Row Level Security (RLS) permitem a operação para o usuário autenticado.
- **Erro de autenticação:** teste com uma conta válida e verifique se a sessão não expirou.

### 7.5. Observações sobre a exportação


O arquivo SQL foi elaborado com base nas colunas, tipos, valores padrão, chaves primárias e chaves estrangeiras consultadas no painel do Supabase.

É importante destacar que esse arquivo não corresponde a um dump integral do banco de dados original.

As políticas de Row Level Security (RLS), triggers, índices adicionais e restrições `CHECK` não foram exportados nem conferidos. Portanto, esses elementos devem ser verificados separadamente no painel do Supabase caso seja necessária uma reprodução integral do ambiente original.

## 8. Segurança

As credenciais de acesso ao Supabase devem ser mantidas em um arquivo `.env` local.

Não compartilhe senhas, tokens, chaves privadas, a chave `service_role` ou dados pessoais dos usuários.

O arquivo `.env` com credenciais reais não deve ser incluído na entrega do projeto. Pode ser enviado apenas o `.env.example`, desde que contenha nomes de variáveis e valores vazios ou fictícios.

## 9. Desenvolvedores

Projeto desenvolvido como Trabalho de Conclusão de Curso por alunas do **3° IPIA**.

## 10. Licença

Projeto desenvolvido para fins educacionais.
