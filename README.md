# EventHub - Plataforma de Gerenciamento de Eventos

## Introdução

EventHub é uma aplicação web robusta desenvolvida para facilitar a descoberta, gerenciamento e participação em eventos. Construída utilizando Node.js e Express.js, a plataforma oferece uma interface intuitiva tanto para usuários finais em busca de eventos quanto para produtores que desejam divulgar e administrar seus próprios eventos. O sistema também conta com um painel administrativo para gerenciamento geral da plataforma. A aplicação utiliza EJS como motor de visualização para renderizar páginas dinâmicas e MySQL como banco de dados para persistência de dados, garantindo uma solução completa e escalável para a gestão de eventos.

## Funcionalidades Principais

A plataforma EventHub engloba um conjunto abrangente de funcionalidades para atender às necessidades de diferentes tipos de usuários:

### Para Usuários Gerais:

*   **Navegação e Descoberta:** Os usuários podem explorar eventos futuros diretamente na página inicial, que exibe os próximos eventos disponíveis. Uma funcionalidade de busca permite filtrar eventos por título, facilitando a localização de interesses específicos. A navegação por gêneros de eventos também está disponível, permitindo uma descoberta categorizada.
*   **Visualização de Detalhes:** Cada evento possui uma página dedicada com informações detalhadas, como descrição, data, hora, local e imagem associada.
*   **Autenticação Segura:** O sistema implementa um fluxo completo de autenticação, permitindo que usuários se cadastrem, façam login e logout de forma segura. As senhas são armazenadas utilizando hash bcrypt para garantir a proteção das credenciais.
*   **Gerenciamento de Conta:** Usuários logados têm acesso a um painel pessoal (dashboard) onde podem visualizar e editar suas informações de perfil, bem como excluir sua conta se desejarem.
*   **Compra de Ingressos:** A plataforma permite a compra de ingressos para os eventos desejados (a lógica exata de pagamento não está detalhada nos arquivos, mas a rota existe).
*   **Meus Ingressos e Feedback:** No painel do usuário, é possível visualizar os ingressos adquiridos e acessar detalhes de cada um. Após participar de um evento, o usuário pode submeter feedback sobre sua experiência.
*   **Favoritos:** Usuários podem marcar eventos como favoritos para fácil acesso posterior, gerenciando sua lista de favoritos através do painel.

### Para Produtores de Eventos:

*   **Registro de Produtor:** Usuários podem se registrar como produtores através de uma seção específica no painel.
*   **Gerenciamento de Eventos:** Produtores logados e registrados podem criar novos eventos, fornecendo detalhes como título, descrição, data, local e imagem (com suporte a upload). Eles também podem editar e excluir os eventos que criaram.
*   **Visualização de Feedback:** Produtores têm acesso ao feedback submetido pelos usuários para os eventos que organizaram, permitindo avaliar a recepção do público.

### Para Administradores:

*   **Painel Administrativo:** Existe uma área de administração separada com login próprio.
*   **Gerenciamento de Usuários:** Administradores podem listar, visualizar detalhes, editar e excluir contas de usuários da plataforma.
*   **Gerenciamento de Conteúdo:** Embora os controllers específicos não tenham sido fornecidos, as rotas indicam que administradores possuem funcionalidades para gerenciar eventos, categorias (gêneros) e feedbacks de toda a plataforma.

## Tecnologias Utilizadas

O EventHub foi desenvolvido utilizando as seguintes tecnologias e bibliotecas:

*   **Backend:** Node.js
*   **Framework Web:** Express.js
*   **Motor de Visualização:** EJS (Embedded JavaScript templates)
*   **Banco de Dados:** MySQL (utilizando o driver `mysql2`)
*   **Gerenciamento de Sessão:** `express-session`
*   **Hashing de Senhas:** `bcrypt`
*   **Upload de Arquivos:** `multer`
*   **Gerenciador de Pacotes:** npm

## Configuração e Instalação

Para executar o projeto EventHub localmente, siga os passos abaixo:

1.  **Pré-requisitos:** Certifique-se de ter o Node.js, npm e um servidor MySQL instalados e em execução no seu ambiente de desenvolvimento.
2.  **Banco de Dados:**
    *   Crie um banco de dados MySQL com o nome `eventhub`.
    *   Importe a estrutura das tabelas e dados iniciais utilizando o arquivo `eventhub.sql` fornecido. Execute o conteúdo deste arquivo no seu cliente MySQL conectado ao banco `eventhub`.
    *   Verifique as credenciais de conexão com o banco de dados no arquivo `db.js`. Por padrão, ele está configurado para conectar-se a `localhost` com o usuário `root` e senha vazia. Ajuste essas configurações conforme necessário para corresponder ao seu ambiente MySQL.
3.  **Dependências:** Navegue até o diretório raiz do projeto no seu terminal e execute o comando `npm install` para baixar e instalar todas as dependências listadas no arquivo `package.json`.
4.  **Execução:** Após a instalação das dependências e configuração do banco de dados, inicie a aplicação executando o comando `npm start` no terminal, a partir do diretório raiz do projeto. Este comando utiliza o script definido no `package.json` para iniciar o servidor Node.js (`node app.js`).
5.  **Acesso:** Uma vez que o servidor esteja em execução (você verá a mensagem "Servidor rodando em http://localhost:3000" no console), abra seu navegador web e acesse `http://localhost:3000` (ou a porta configurada, caso seja diferente) para interagir com a aplicação EventHub.

## Uso

Após iniciar a aplicação, você pode navegar pelas diferentes seções:

*   **Página Inicial:** Explore os eventos futuros ou use a barra de busca.
*   **Login/Registro:** Crie uma nova conta ou faça login com uma conta existente para acessar funcionalidades personalizadas.
*   **Painel do Usuário:** Acesse `/user/dashboard` após o login para gerenciar sua conta, ingressos, favoritos e registrar-se como produtor.
*   **Painel do Produtor:** Dentro do dashboard, acesse as opções de produtor para criar e gerenciar seus eventos.
*   **Painel Administrativo:** Acesse `/admin/login` para entrar na área de administração (requer credenciais de administrador, que podem precisar ser criadas manualmente no banco de dados inicialmente).

