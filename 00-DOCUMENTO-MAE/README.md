# GESTÃO DE MARMORARIA — DOCUMENTO-MÃE
## ARQUITETURA MULTIEMPRESA (MULTITENANT) — VERSÃO 1.0
**Empresa inicial de implantação:** PORCELANE

---

## ÍNDICE GERAL
1. PRINCÍPIOS E ARQUITETURA
2. ETAPA 01 — GITHUB — BASE OFICIAL DO SISTEMA
3. ETAPA 02 — DIFY — 22 AGENTES DO SISTEMA
4. ETAPA 03 — SUPABASE — BANCO MULTITENANT
5. ETAPA 04 — LOVABLE — INTERFACE E EXPERIÊNCIA

---

# PRINCÍPIOS E ARQUITETURA
## Definição Fundamental
✅ **Gestão de Marmoraria** = Nome oficial do produto/sistema.
✅ **Porcelane** = Primeira empresa cadastrada, implantação inicial.
❌ Porcelane **não é o sistema**, é uma empresa dentro do sistema.

## Estrutura Hierárquica
GESTÃO DE MARMORARIA (SISTEMA)
│
├── EMPRESA 01 → PORCELANE (implantação inicial)
│   ├── Dados da empresa
│   ├── Clientes
│   ├── Obras
│   ├── Orçamentos
│   ├── Pedidos
│   ├── Técnico
│   ├── Produção
│   ├── Qualidade
│   ├── Expedição
│   ├── Financeiro
│   ├── Estoque
│   ├── Documentos
│   ├── Arquivos/Imagens
│   ├── Relatórios
│   └── Configurações próprias
│
├── EMPRESA 02 → Marmoraria Silva
│   ├── Dados próprios
│   ├── Clientes próprios
│   └── Demais módulos isolados
│
└── EMPRESA 03 → Marmoraria Oliveira
    ├── Dados próprios
    ├── Clientes próprios
    └── Demais módulos isolados

## 6 Camadas de Separação
1. **Sistema** — Regras gerais, fluxos, estrutura, agentes, funcionalidades.
2. **Empresa** — Registro da marmoraria com identificador único `tenant_id`.
3. **Dados da Empresa** — Clientes, obras, pedidos, materiais, documentos, histórico.
4. **Configurações da Empresa** — Logo, cores, dados fiscais, regras comerciais, comissão, formas de pagamento.
5. **Conhecimento Técnico Global** — Terminologia, acabamentos, normas de marmoraria (compartilhado por todas).
6. **Conhecimento Particular da Empresa** — Tolerâncias, regras internas, procedimentos exclusivos.

## Regra dos Agentes
Os 22 agentes pertencem ao **sistema Gestão de Marmoraria**.
- Recebem o contexto `tenant_id` da empresa ativa.
- Consultam regras globais + configurações da empresa.
- Executam ações no ambiente isolado daquela empresa.
- Nenhum dado é compartilhado entre empresas.

## Regra de Isolamento
Dados, configurações, arquivos e histórico de uma empresa **nunca** são visíveis por outra.
