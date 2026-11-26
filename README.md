# HelpYou — Plataforma de Estudos

## 1. Sobre o projeto

O **HelpYou** é uma plataforma de estudos desenvolvida para auxiliar estudantes na preparação para vestibulares e outros processos seletivos. A proposta é reunir conteúdos educacionais e ferramentas de organização em um único ambiente, facilitando o planejamento da rotina de estudos e o acompanhamento do progresso.

O projeto foi desenvolvido como Trabalho de Conclusão de Curso (TCC) por estudantes do curso Técnico de Informática para a Internet.

## 2. Objetivos

- Disponibilizar conteúdos educacionais organizados por disciplinas.
- Facilitar o planejamento e a organização da rotina de estudos.
- Apoiar a preparação para vestibulares e processos seletivos.
- Permitir o acompanhamento dos registros e do progresso de estudo.
- Incentivar a autonomia e a organização dos estudantes.

## 3. Funcionalidades

A plataforma reúne as seguintes funcionalidades:

- **Cadastro e login:** criação de conta e autenticação para acessar a plataforma.
- **Matérias e conteúdos:** acesso a materiais de estudo organizados por disciplinas.
- **Cronograma:** organização e planejamento da rotina de estudos.
- **Desempenho:** acompanhamento das atividades e dos registros de estudo.
- **Perfil:** visualização e edição das informações da conta.
- **Contato:** formulário para envio de mensagens à equipe responsável pelo projeto.

## 4. Tecnologias utilizadas

### Front-end
- HTML5
- CSS3
- JavaScript
- Bootstrap

### Back-end
- Node.js
- Express

### Banco de dados e autenticação
- Supabase
- PostgreSQL

## 5. Estrutura do projeto

Os arquivos estão organizados em diretórios de acordo com suas funções:

| Diretório/arquivo | Descrição |
|---|---|
| `css/` | Folhas de estilo utilizadas na interface. |
| `js/` | Scripts JavaScript do front-end. |
| `img/` | Imagens e recursos visuais. |
| `fontes/` | Arquivos de fontes utilizados no projeto. |
| `pages/` | Páginas internas da plataforma. |
| `server/` | Arquivos relacionados ao servidor e ao back-end. |
| `index.html` | Página inicial da aplicação. |
| `package.json` | Dependências e scripts de execução do projeto. |
| `package-lock.json` | Registro das versões instaladas das dependências. |
| `.env` | Variáveis de ambiente necessárias à configuração dos serviços. |

## 6. Como executar o projeto

### 6.1. Pré-requisitos

Para executar o HelpYou, é necessário ter:

- [Node.js](https://nodejs.org/) instalado (foi utilizado Node.js 24.15.0 no desenvolvimento).
- npm, instalado junto com o Node.js.
- [Visual Studio Code](https://code.visualstudio.com/) ou outro editor de código.
- Um navegador de internet.

### 6.2. Abrir o projeto

1. Extraia o arquivo compactado do HelpYou, caso tenha recebido o projeto em ZIP.
2. Abra a pasta principal do projeto no Visual Studio Code.
3. Abra o terminal integrado do editor (**Terminal > Novo Terminal**).
4. Confira se o terminal está na pasta em que se encontra o arquivo `package.json`.

### 6.3. Instalar as dependências

No terminal, execute:

```bash
npm install
```

Esse comando instala as bibliotecas necessárias, de acordo com as dependências declaradas no `package.json`.

### 6.4. Configuração do ambiente

O projeto utiliza variáveis de ambiente para acessar os serviços integrados, incluindo o Supabase e o serviço de envio de e-mails.

O arquivo `.env` acompanha a versão disponibilizada para execução. Ele deve permanecer na pasta principal do projeto, no mesmo nível do `package.json`. Não altere os nomes das variáveis sem atualizar também o código que as utiliza.

### 6.5. Iniciar o back-end

Com o terminal aberto na pasta principal do projeto, execute:

```bash
npm run dev
```

Esse comando inicia o servidor de desenvolvimento do Node.js. Na configuração utilizada pelo projeto, o servidor fica disponível em:

```text
http://localhost:3000
```

Mantenha esse terminal aberto enquanto estiver utilizando a plataforma. Para encerrar o servidor, pressione `Ctrl + C` no terminal.

### 6.6. Acessar a plataforma

Após iniciar o servidor, abra no navegador o endereço disponibilizado pela aplicação:

```text
http://localhost:3000
```

Caso a página inicial não seja exibida nesse endereço, verifique a configuração de rotas e de arquivos estáticos do servidor antes de utilizar outro método para abrir o front-end.

## 7. Integração com serviços externos

O HelpYou utiliza o **Supabase** para os recursos de banco de dados e autenticação. O projeto também possui configuração de envio de mensagens por e-mail para o formulário de contato.

As configurações necessárias para essas integrações são lidas pelo projeto a partir das variáveis de ambiente do arquivo `.env`. Para executar a aplicação, mantenha esse arquivo na pasta principal e utilize as configurações fornecidas com a versão do projeto.

## 8. Observações e solução de problemas

- **O comando `npm` não é reconhecido:** verifique se o Node.js está instalado corretamente e reinicie o terminal.
- **Erro ao instalar dependências:** confira se o terminal está na pasta que contém o `package.json` e execute novamente `npm install`.
- **O servidor não inicia:** confira as mensagens exibidas no terminal e verifique se a porta utilizada pelo servidor não está ocupada.
- **Erro de conexão com o Supabase:** confira se o arquivo `.env` está na pasta principal e se as variáveis de ambiente estão preenchidas corretamente.
- **Erro ao enviar mensagens pelo formulário:** confira as configurações de e-mail presentes no ambiente e as mensagens de erro exibidas pelo servidor.
- **A página não abre ou não carrega os recursos:** confirme que o servidor back-end está em execução e que as rotas e os arquivos estáticos estão configurados corretamente.
- **Erro de acesso ou permissão nos dados:** verifique a autenticação da conta e as permissões configuradas no serviço Supabase.

## 9. Segurança

O arquivo `.env` contém configurações de acesso a serviços utilizados pela aplicação. Não publique esse arquivo em repositórios públicos nem compartilhe suas credenciais fora do contexto autorizado para a avaliação do projeto.

## 10. Desenvolvedores

Projeto desenvolvido como Trabalho de Conclusão de Curso por estudantes do curso Técnico de Informática para a Internet.

## 11. Finalidade

Este sistema foi desenvolvido para fins educacionais, como parte das atividades do Trabalho de Conclusão de Curso.
