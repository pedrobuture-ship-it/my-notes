# prs

Atualize a vitrine e o fluxo de contratação (/comprar) do PRS Cloud para suportar a nova variação `premium` da tag `[kanban]` vinda da coluna `descricao` dos projetos cadastrados no Gestor.

Contexto do que vem da API (coluna `descricao` do Projeto no Gestor):
- `[kanban] basico` -> Versão Básica (exibida no Passo 1 como card principal)
- `[kanban] pro` -> Versão PRO (com `[ocultar_card]` para não duplicar no Passo 1)
- `[kanban] premium` -> Nova versão Premium (também com `[ocultar_card]` para não duplicar no Passo 1)

O que precisa ser ajustado no front-end (`prsfront`):
1. Parser de tags da `descricao` do projeto:
   - Passar a reconhecer `[kanban] premium` além de `basico` e `pro`.
   - Garantir que projetos com `[ocultar_card]` continuem ocultos no Passo 1 (Escolha do Sistema).

2. Passo 2 (Escolha do Plano / Seletor em abas/pills do Kanban):
   - Além das abas **Básica** e **PRO**, adicionar suporte à terceira aba **Premium** quando existir um projeto ativo com `[kanban] premium`.
   - Ao selecionar a aba **Premium**, exibir os planos e valores vindos da Tabela de Preços vinculada a esse projeto `[kanban] premium`, bem como seus respectivos benefícios (`[check]`), `[faixa]` e `[unidade]`.
   - Caso não exista nenhum projeto com `[kanban] premium` cadastrado/ativo, exibir normalmente apenas as abas existentes (retrocompatibilidade).

3. Fluxo de seleção e checkout:
   - Garantir que, ao escolher um plano na aba **Premium**, o ID do projeto (`projetoId`) e os dados do plano selecionado sejam enviados corretamente para as etapas seguintes da contratação.

Observação: Os preços exibidos continuam vindo exclusivamente da Tabela de Preços do Gestor (a tag `[preco]` não é mais utilizada).