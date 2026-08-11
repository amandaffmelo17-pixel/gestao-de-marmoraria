# GESTÃO DE MARMORARIA — REGRAS GERAIS DO SISTEMA
## VERSÃO 1.0

### OBJETIVO
Definir as regras universais do sistema **Gestão de Marmoraria**, válidas para todas as empresas cadastradas. Nenhuma regra aqui é exclusiva da Porcelane.

### PRINCÍPIOS GERAIS
1. O sistema opera em arquitetura **multitenant** — cada empresa é isolada por `tenant_id`.
2. Dados de uma empresa **nunca** são acessíveis por outra.
3. Os 22 agentes seguem as mesmas regras globais + regras específicas da empresa.
4. Identificadores sequenciais reiniciam por empresa: `ORC-000001`, `PED-000001`, etc.
5. Todo registro operacional **deve conter** o campo `tenant_id`. Sem ele, não é salvo.

### FLUXO OPERACIONAL PADRÃO
Orçamento → Aprovação → Gera Pedido → Levantamento → Liberação Técnica → Produção → Qualidade → Expedição → Instalação → Financeiro.

### CONHECIMENTO TÉCNICO GLOBAL
Compartilhado entre todas as empresas: terminologia, tipos de acabamento, tipos de borda, tabelas de medição, normas de corte e colagem, tolerâncias padrão, nomenclatura de materiais.

### REGRAS DE SEGURANÇA
- `tenant_id` não pode ser alterado após criação.
- Log de auditoria registra quem, quando e o que foi alterado.
- Permissões por perfil: Administrador, Comercial, Técnico, Produção, Financeiro, Leitor.

### PADRÃO DE DOCUMENTOS
- Orçamentos, pedidos e documentos carregam a identidade visual da empresa.
- Numeração sequencial própria por empresa.
- Histórico de alterações vinculado ao `tenant_id`.
