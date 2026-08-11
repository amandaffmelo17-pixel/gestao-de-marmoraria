# GESTÃO DE MARMORARIA — OS 22 AGENTES DO SISTEMA
## VERSÃO 1.0

### REGRA GERAL
Todos os agentes recebem o `tenant_id` e operam SOMENTE dentro do ambiente daquela empresa. Consultam conhecimento global + regras específicas da empresa.

---

### 🤖 LISTA DOS 22 AGENTES

**01. Orquestrador Geral**
Recebe a demanda, identifica o `tenant_id`, entende o assunto e encaminha ao agente especialista correto.

**02. Padrão do Sistema**
Garante consistência em nomes, formatos, códigos, numeração e visual.

**03. Clientes / CRM**
Cadastro, consulta, histórico, etiquetas e classificação de clientes da empresa.

**04. Comercial / Orçamentos**
Elabora orçamentos, aplica tabela de preços da empresa, calcula materiais, mão de obra, prazo. Envia para aprovação.

**05. Obras**
Cadastra obra, endereço, ambientes, medidas, responsável, status e prazo.

**06. Técnico de Marmoraria**
Analisa viabilidade, valida medidas, indica espessura, tipo de borda, cola, suporte, risco de fissura. Libera ou não.

**07. Levantamento / Medição**
Registra medidas, planta, fotos, pontos de luz, tomadas, ralos, torneiras. Gera ficha técnica.

**08. Produção / Produtividade**
Programa corte, alocação de chapas, ordem de fabricação, acompanhamento de etapas, tempo e perdas.

**09. Qualidade**
Inspeção por etapa, registro de não conformidades, retrabalho, liberação final ou devolução.

**10. Expedição / Romaneio**
Conferência de peças, embalagem, carregamento, romaneio de saída e conferência no destino.

**11. Instalação / Pós-Obra**
Agenda instalação, acompanha execução, recebe aceite, registra garantia e pós-venda.

**12. Pessoas / Comportamento**
Escala, capacidade, carga de trabalho, prevenção de sobrecarga, clima e desenvolvimento.

**13. Financeiro**
Condição de pagamento, entrada, parcelas, vencimentos, recebíveis, baixas e inadimplência.

**14. Comissionamento**
Calcula comissão conforme regra da empresa (por vendedor, tipo de obra, faixa de valor).

**15. Comunicação Omnichannel**
Envia mensagens automáticas por WhatsApp, e-mail, Instagram com identidade visual da empresa.

**16. Documentos / PDF**
Gera orçamentos, pedidos, contratos e fichas em PDF com marca e dados da empresa.

**17. Estoque / Materiais**
Entrada, saída, saldo, reservas, chapas, blocos, cola, abrasivos e insumos.

**18. Compras / Fornecedores**
Cotação, acompanhamento de pedidos, prazos de entrega, preços e histórico.

**19. Suporte / Diagnóstico**
Recebe problemas, classifica, busca solução e registra para melhoria contínua.

**20. Segurança / Auditoria**
Logs de acesso, alterações, permissões por perfil e rastreabilidade completa por `tenant_id`.

**21. Gestão / Indicadores**
Faturamento, margem, taxa de aprovação, prazo médio, produtividade e inadimplência.

**22. Integrações / Automação**
APIs, webhooks, disparos automáticos e sincronização entre sistemas.
