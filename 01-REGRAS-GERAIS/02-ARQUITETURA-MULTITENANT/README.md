# GESTÃO DE MARMORARIA — ARQUITETURA MULTITENANT
## VERSÃO 1.0

### CONCEITO PRINCIPAL
O sistema é **multiempresa (multitenant)**: uma única instalação serve várias marmorarias independentes, com dados totalmente isolados.

### IDENTIFICADOR ÚNICO — tenant_id
Cada empresa recebe um **código único** chamado `tenant_id` (UUID).
- TODO dado, TODO registro, TODO arquivo pertence a um `tenant_id`.
- Sempre que um agente ou usuário consulta dados, ele filtra pelo seu `tenant_id`.
- Nenhum dado cruza entre empresas.

### ESTRUTURA DE ISOLAMENTO
1. **Camada do Sistema** — Código, regras globais, agentes, fluxos. Compartilhado.
2. **Camada da Empresa** — Cadastro, configurações, identidade visual. Isolado.
3. **Camada de Dados** — Clientes, obras, orçamentos, pedidos. Isolado.
4. **Camada de Conhecimento Particular** — Regras internas, tolerâncias, preços próprios. Isolado.

### COMO FUNCIONA NA PRÁTICA
- Usuário faz login → sistema identifica seu `tenant_id`.
- Tudo que ele vê, cria ou altera → vinculado ao mesmo `tenant_id`.
- Políticas de segurança (RLS) no banco de dados BLOQUEIAM acesso cruzado.
- Sequências numéricas reiniciam em cada empresa: `ORC-000001` para Porcelane, `ORC-000001` também para Marmoraria Silva — sem conflito.

### REGRA DE OURO
> Se não tem `tenant_id`, não existe. Se tem, pertence SOMENTE àquela empresa.
