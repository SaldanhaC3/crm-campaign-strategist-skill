# Compliance e Deliverability (2026)

Campanha que não chega à inbox tem lift zero. Deliverability e base legal são pré-requisitos de estratégia, não detalhe técnico.

## Requisitos Gmail/Yahoo para bulk senders (enforcement 2026)

- **Autenticação obrigatória**: SPF + DKIM (chave ≥1024 bits; recomendado 2048) + DMARC. Desde nov/2025 o Google passou de atrasos temporários a rejeições permanentes para configuração incompleta.
- **One-click unsubscribe (RFC 8058)**: headers `List-Unsubscribe` + `List-Unsubscribe-Post` — link no rodapé NÃO basta. Processar o opt-out em até 2 dias.
- **Spam complaint rate**: limite duro 0,3%; senders estáveis operam **abaixo de 0,1%** — usar esta como meta. Complaint subindo = reduzir frequência e reforçar segmentação ANTES de queimar o domínio.
- Higiene: sunset de inativos (3–4 tentativas de win-back sem resposta → supressão), double opt-in quando possível, warm-up de domínio/IP novo.

## LGPD (Brasil) — base legal para CRM

- Todo tratamento precisa de base legal; para email/SMS marketing a base realista é **consentimento dado ao próprio remetente** — não a um parceiro, broker ou "implícito" de cadastro público. **Lista comprada = violação direta.**
- Documentar quando/como o consentimento foi obtido e a finalidade; registrar mudanças de preferência.
- Legítimo interesse pode amparar comunicação a clientes ativos sobre produtos similares (soft opt-in), mas exige teste de balanceamento documentado e opt-out fácil em toda mensagem.
- Direitos do titular (acesso, correção, revogação, exclusão) devem ser executáveis — revogou, saiu de TODAS as réguas promocionais.
- WhatsApp: exige opt-in próprio do canal e uso de templates aprovados fora da janela de 24h de atendimento.

## Regras derivadas para a skill

1. Toda campanha proposta assume base opt-in própria; se o usuário mencionar lista comprada/cedida, alertar sobre LGPD antes de estrategiar.
2. Recomendar sempre: monitoramento de complaint rate por régua e sunset automático de inativos.
3. Volume/frequência propostos devem manter complaint <0,1% — em caso de sinal de fadiga, aplicar os descansos de `reguas-e-timings.md`.
4. Incluir no plano de medição a checagem de deliverability (inbox placement, bounce <2%) antes de interpretar lift.
