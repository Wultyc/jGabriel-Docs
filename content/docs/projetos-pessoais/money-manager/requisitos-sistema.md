---
title: "Requisitos Sistema"
weight: 3
bookCollapseSection: false
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---
## Propósito geral do sistema
Sistema de registo de transações financeiras alojado na cloud.

## User Stories

### Utilizador
- Como utilizador eu pretendo poder registar as minhas transacções financeiras (receitas, despesas e transferências). Assim posso manter um histórico de transações
- Como utilizador eu pretendo ter alguns gráficos e resumos das minhas transições financeiras em diferentes momentos do tempo para assim poder analisar o meu passado financeiro.
- Como utilizador pretendo poder fazer o download dos meus dados na aplicação. Assim posso saber exactamente o que aplicação "sabe" sobre mim e posso fazer uma analise própria dos dados.
- Como utilizador pretendo poder apagar informações próprias da aplicação. Assim posso controlar que a minha informação registada no sistema é aquela que eu quero.
- Como utilizador pretendo poder carregar um ficheiro de dados para inserir múltiplos registos ao mesmo tempo. Assim poderia restaurar uma cópia de segurança dos meus dados.
- Como utilizador pretendo poder escolher se apago os registos antigos no momento de upload de um ficheiro de dados. Assim posso prever melhor qual o resultado no final da operação.
- Como utilizador pretendo poder categorizar (em categorias e sub-categorias) cada um dos meus movimentos para assim organizar melhor a minha informação.
- Como utilizador pretendo poder criar, editar e apagar categorias de movimentos para assim personalizar melhor os modo como a minha informação é organizada.
- Como utilizador pretendo poder criar várias contas . Assim poderei separar os movimentos financeiros.
- Como utilizador pretendo ter alguns gráficos e resumos das minhas das minhas costas o para assim poder analisar de um modo rápido o estado de cada uma.
- Como utilizador pretendo que a aplicação se adapte bem a todos os tipos de dispositivos onde eu a possa aceder.
- Como utilizador pretendo poder definir alertas para assim ser avisado movimentos recorrentes e/ou excesso de gastos.
- Como utilizador pretendo poder atualizar as minhas informações pessoais.

### Gestor de Conta
- Como gestor de conta pretendo controlar as permissões de (leitura e escrita) de cada uma das minhas contas individualmente. Assim poderei controlar mais eficazmente as alterações que são feitas.
- Como gestor de conta pretendo poder adicionar e remover utilizadores das minhas contas. Assim tenho um melhor controlo de quem tem acesso à informação da conta.
- Como gestor de conta pretendo controlar as categorias que os registos podem ou não ter.
- Como gestor de conta pretendo poder exigir que os movimentos seja aprovados ou revistos. Assim posso ter controlar de forma mais efetiva a informação na conta.
- Como gestor de conta pretendo poder nomear um novo gestor de conta. Assim posso dividir as responsabilidades com uma ou mais pessoas.
- Como gestor de conta pretendo poder definir alertas. Assim posso ser notificado com informações sobre as minhas contas.
- Como gestor de conta pretendo poder atualizar as informações da minha conta. Assim tenho a certeza que tudo estará sempre atualizado.

### Gestor de Organização
- Como gestor de organização pretendo poder atualizar as informações da minha organização. Assim tenho a certeza que tudo estará sempre atualizado.
- Como gestor de organização pretendo poder criar novas contas e nomear os respetivos administradores. Assim posso organizar de forma mais eficiente os movimentos da minha organização.
- Como gestor de organização pretendo ter os mesmo poderes que os gestores das minhas contas.
- Como gestor da organização pretendo poder adicionar e remover utilizadores da minha organização. Assim posso controlar melhor quem acede as minhas contas.
- Como gestor de organização pretendo que as minhas contas apenas possam ser acedidas por outros utilizadores da minha organização. Assim tenho controlo sobre quem pode aceder às informações da minha organização.
- Como gestor de organização pretendo poder distinguir os utilizadores por cargos e limitar as suas permissões por via desses cargos.
- Como gestor de organização pretendo poder exigir aprovação sobre alterações significativas nas contas da minha organização. Assim posso evitar algum tipo de perda de informação.
- Como gestor de conta pretendo poder nomear um novo gestor de organização. Assim posso dividir as responsabilidades com uma ou mais pessoas.

### Administrador de Sistema
- Como administrador de sistema pretendo poder controlar as permissões de cada tipo de utilizador. Assim posso manter a segurança e integridade das informações no sistema.
- Como administrador pretendo poder adicionar/remover/desativar/ativar utilizadores do sistema. Assim posso ter um controlo mais efetivo sobre quem utiliza e como utiliza a aplicação.


## Use Cases
Com base nas user stories descritas acima, foram determinados os seguintes use cases
{{<figure src="/images/money-manager/3.1_Diagrama-de-Use-Cases.png">}}

## Diagrama de Sistema  
Analisados os pontos anteriores, fica claro que o sistema terá 3 entidades distintas: User, Organization, Account, Transaction e . Não foi definido uma entidade para o cargo de Gestor de Conta e Gestor de Organização porque essas características vão ser definidas através de cargos das próprias contas/organizações. Além de simplificar as relações entre as entidades, esta solução permite ainda que um utilizador com um cargo mais elevado numa organização não tenha os mesmos poderes noutra organização.
{{<figure src="/images/money-manager/3.2_Diagrama-de-Sistema.png">}}

## Lista completa de requisitos
A lista final de requisitos do sistema é a seguinte:  
- Utilizador
    - Tem de se autenticar sempre que pretende utilizar o sistema

- Gestor de Conta
    - Identificado pelo seu Role.
    - Alterar permissões dos utilizadores da conta
    - Adicionar/remover utilizadores da conta
    - Atualizar informações de conta

- Gestor da Organização
    - Identificado pelo seu Role.
    - Alterar permissões dos utilizadores da organização
    - Adicionar/remover utilizadores da organização
    - Atualizar informações das contas
    - Atualizar informações da organização

- Administrador de Sistema
    - Listar, criar e apagar utilizadores.
    - Alterar as permissões padrão do sistema.

- Transação
    - Registo do id de utilizador, a conta a que pertence, período de transação, data de transação, descrição, uma categoria, o valor da transação, o saldo antes e após a transação e se era uma transação planeada.
    - Ver, editar e apagar registos.
    - Em caso de ser uma transferência, devem ser ainda registados os ID da transação com a qual se relacionam.
    - Fazer o download dos registos em formato CSV e PDF.
    - Carregar ficheiros CSV com informação.
    - Permitir que o utilizador escolha se quer limpar o registo da conta no momento do upload.
    - As transações devem ser aprovadas se o gestor assim definir.
    - Nomear novo gestor.
    - O período da transação deve ser preenchido automaticamente com a informação padrão.
    - Quando o período de transação é alterado, o utilizador deve ser questionado se pretende atualizar o período de transação padrão da conta, caso tenha permissão para isso.
    - As transações só devem ser editadas/apagadas por quem as inseriu.

- Categorias
    - Ver, criar, editar e apagar categorias.
    - Categorias podem ter até um subnível.
    - Categorias são vinculadas a 1 conta.
    - Uma categoria só pode ser apagada se não existir nenhum registo a ela associado.

- Contas
    - Cada conta deve ter uma página de gráficos de analise e uma página com relatórios sob a forma de tabelas.
    - As contas podem ser abertas e fechadas
    - As contas devem possuir os parâmetros para definir informações globais como: período da transação, estado da conta, saldo atual, obrigatoriedade na aprovação de registos.
    - Contas só podem ser acedidas por utilizadores da mesma organização.

- Organização
    - Cada organização deve ter uma página de gráficos de analise e uma página com relatórios sob a forma de tabelas.

- *Roles*
    - Deve existir um conjunto de definições padrão pré-configuradas no sistema.
    - Sempre que é criada uma organização ou conta, as permissões iniciais devem ser iguais às permissões padrão do sistema.
    - Devem existir os seguintes perfis: Administrador (adm), Gestor de Organização (org_man), Gestor de conta (act_man), Utilizador normal, (user), Utilizador Convidado (guest)
    - Os utilizadores de perfis Administrador, Gestor de Organização, Gestor de conta e Utilizador normal, deverão ter as suas permissões padrão definidas conforme os requisitos dos seus perfis conforme indicado nos outros campos. Os utilizadores convidados deverão, por padrão, ter apenas permissões de leitura.

- Permissões
    - Conta
        - Ver registos
        - Inserir registos
        - Editar registos
        - Apagar registos
        - Download de registos
        - Upload de ficheiros de dados
        - Criar categorias
        - Editar categorias
        - Apagar categorias
        - Atualização das permissões dos utilizadores da conta
        - Listar utilizadores da conta
        - Adicionar/Remover utilizadores da conta
        - Atualizar informações de conta
        - Definir período da transação padrão
    - Organização
        - Criar contas
        - Fechar contas
        - Atualização das permissões
        - Listar utilizadores da organização
        - Adicionar/Remover utilizadores da organização
        - Atualização das permissões dos utilizadores da organização
        - Atualizar informações de conta
        - Atualizar informações das contas da organização
    - Utilizador
        - Atualizar informação pessoal
    - Sistema
        - Listar utilizadores.
        - Criar utilizadores.
        - Apagar utilizadores.
        - Modificar as permissões padrão do sistema.

- Sistema Base
    - Tem de possuir um sistema de autenticação
    - Interface adaptável a sistemas Desktop e Mobile.
    - Sempre que um registo é apagado, este deve ser conservado na base de dados e deve ser definido o valor da coluna “deleted_at”.

- Base de Dados
    - Todos os registos devem ter uma chave primária (ID)
    - Todos as tabelas devem possuir os campos “created_at”, “updated_at” e “deleted_at”

## Lista de requisitos a incluir numa versão futura
Em versões futuras, os seguintes requisitos deverão ser incluidos
- Alertas	
    - Definir, ver, editar e apagar alertas
- Gestor de Organização	
    - Exigir aprovação na atualização das informações das contas
- Aplicação
    - Cliente CLI em Python