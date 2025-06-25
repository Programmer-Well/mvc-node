# Lista de Tarefas - Aplicação Web com Node.js, Express.js e EJS

Este projeto é uma simples aplicação web de lista de tarefas, construída para fins de aprendizado e prática de desenvolvimento backend com Node.js, Express.js e EJS. A aplicação utiliza a arquitetura MVC (Model-View-Controller) para uma organização clara e manutenção facilitada do código.

## Tecnologias Utilizadas

*   **Node.js:** Ambiente de execução JavaScript no servidor.
*   **Express.js:** Framework web para Node.js, que simplifica a criação de aplicações web.
*   **EJS (Embedded JavaScript templating):** Mecanismo de template para gerar páginas HTML dinâmicas.
*   **Bootstrap (opcional):** Framework CSS para estilização e responsividade da interface.

## Estrutura do Projeto

A aplicação segue a estrutura MVC (Model-View-Controller):

*   **`models/tarefaModel.js`:**
    *   Responsável por armazenar e manipular os dados das tarefas.
    *   Atualmente, as tarefas são armazenadas em um array em memória (`let tarefas = []`).
    *   Funções:
        *   `adicionarTarefa(descricao)`: Adiciona uma nova tarefa ao array, gerando um ID único (usando `Date.now()`).
        *   `obterTarefas()`: Retorna a lista de tarefas.
        *   `removerTarefa(id)`: Remove uma tarefa com base no seu ID.
        *   `alterarTarefa(id)`: (Implementação futura) Função para alterar a tarefa.

*   **`controllers/tarefaController.js`:**
    *   Controla a lógica de negócios e a interação entre o Model e a View.
    *   Funções:
        *   `exibirTarefas(req, res)`: Renderiza a view `index.ejs`, passando a lista de tarefas para ela.
        *   `adicionarTarefa(req, res)`: Recebe a descrição da tarefa do corpo da requisição (usando `body-parser`), adiciona a tarefa ao Model e redireciona para a página principal.
        *   `removerTarefa(req, res)`: Recebe o ID da tarefa da requisição, remove a tarefa do Model e redireciona para a página principal.
        *   `alterarTarefa(req, res)`: (Implementação futura) Função para alterar a tarefa.

*   **`views/` (arquivos EJS):**
    *   Contém os templates EJS para renderizar as páginas HTML dinâmicas.
        *   `index.ejs`: Exibe a lista de tarefas, o formulário para adicionar tarefas e links para remover/alterar tarefas (com HTML e Bootstrap, se usado).
        *   `adicionarTarefa.ejs`: Exibe o formulário para adicionar tarefas.
        *   `alterarTarefa.ejs`: (Implementação futura) Exibirá o formulário para alterar as tarefas.

*   **`app.js`:**
    *   Configura o servidor Express.
    *   Define as rotas (URLs) e associa-as aos métodos do controller.
    *   Utiliza o `body-parser` para analisar os dados enviados via formulários.
    *   Configura o EJS como o mecanismo de template.
    *   Define o diretório `public` para servir arquivos estáticos (CSS, JavaScript, imagens).
    *   Inicia o servidor na porta especificada (por padrão, 3000).

## Funcionalidades

*   **Adicionar Tarefa:**
    *   Um formulário permite que os usuários insiram uma descrição para uma nova tarefa.
    *   Ao enviar o formulário, a descrição é recebida pelo controller, a tarefa é adicionada ao Model e o usuário é redirecionado para a página principal.
*   **Listar Tarefas:**
    *   A página principal (`/`) exibe uma lista com todas as tarefas cadastradas.
    *   Cada tarefa exibida inclui a descrição e links para remover/alterar (ainda não implementada) a tarefa.
*   **Remover Tarefa:**
    *   Ao clicar no link "Remover" ao lado de uma tarefa, a aplicação remove a tarefa com base no seu ID.
    *   O usuário é redirecionado para a página principal após a remoção.
*   **(Futuramente) Alterar Tarefa:**
    *   (A ser implementado) Um modal com um formulário será exibido ao clicar no link "Alterar" de uma tarefa.
    *   O formulário permitirá que o usuário edite a descrição da tarefa.
    *   Ao salvar as alterações, a tarefa será atualizada e a lista de tarefas será atualizada.

## Como Executar o Projeto

1.  **Pré-requisitos:**
    *   Node.js e npm (Node Package Manager) instalados.
2.  **Instalação:**
    *   Clone este repositório: `git clone <URL_DO_SEU_REPOSITORIO>` (substitua `<URL_DO_SEU_REPOSITORIO>` pela URL do seu repositório Git).
    *   No terminal, navegue até o diretório do projeto: `cd <nome_do_seu_projeto>`.
    *   Execute `npm install` para instalar as dependências (express, ejs, body-parser).
3.  **Execução:**
    *   Execute `node app.js` no terminal para iniciar o servidor.
    *   Abra seu navegador e acesse `http://localhost:3000` para visualizar a aplicação.

## Próximos Passos e Melhorias

*   Implementar a funcionalidade de alterar tarefa (com modal e formulário).
*   Adicionar validação de dados (por exemplo, verificar se a descrição da tarefa não está vazia).
*   Melhorar a persistência dos dados (armazenar as tarefas em um banco de dados, como um arquivo JSON, MongoDB ou PostgreSQL, em vez de usar um array em memória).
*   Implementar um sistema de autenticação (para restringir o acesso a usuários autenticados).
*   Adicionar testes unitários.

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para:

1.  Fazer um fork deste repositório.
2.  Criar uma branch para suas alterações (`git checkout -b sua-branch`).
3.  Fazer commit de suas alterações (`git commit -m "Sua descrição"`).
4.  Enviar um pull request.

---
