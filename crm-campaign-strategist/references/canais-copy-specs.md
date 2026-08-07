# Especificações de Copy por Canal

Os 6 canais da operação: **push (app), banner in-app, email, SMS, WhatsApp, DM**. Cada texto entregue deve respeitar o formato do canal — copy boa no canal errado é copy ruim.

## ANTES DE ESCREVER: confirmar os limites com o usuário

Os limites de caracteres variam por plataforma/ferramenta de disparo e por template. **Na primeira campanha de cada operação, PERGUNTE ao usuário os limites reais dos canais que serão usados** (título/corpo de push, headline/sub/CTA de banner, assunto/preheader de email, segmento de SMS, corpo/botões de WhatsApp, DM). Use AskUserQuestion quando disponível; senão pergunte em texto.

- Grave as respostas em `learnings/config-canais.md` no diretório de trabalho, no formato: canal → campo → limite → data.
- Nas campanhas seguintes, **use a configuração gravada sem perguntar de novo** — pergunte apenas se surgir canal novo ou se o usuário mencionar mudança de ferramenta/template.
- Os números abaixo são **defaults de mercado, usados apenas como fallback** quando o usuário não souber ou não responder — e nesse caso, sinalize na entrega que foram usados defaults.
- O gate G1 do pipeline de validação valida contra a configuração do usuário, não contra os defaults.

## Push notification (app)

- **Título**: até ~35 caracteres (corta no Android/iOS). **Corpo**: até ~120 caracteres visíveis; o essencial nos primeiros 60.
- Estrutura: gancho pessoal/urgente no título + benefício ou curiosidade no corpo + deep link para a ação exata.
- Sem saudação, sem assinatura, sem link escrito. Emoji: no máximo 1, com função.
- Papel na régua: gatilho de tempo real (evento em 1h, carrinho quente, novidade). É interrupção — só dispara com relevância alta e respeito rígido ao frequency cap.
- Anti-padrão: título genérico ("Temos novidades!"), pedir abertura sem entregar valor no próprio texto.

## Banner in-app

- **Headline**: até ~40 caracteres. **Sub**: até ~90. **CTA no botão**: 1–3 palavras, verbo no imperativo ("Resgatar", "Ver oferta").
- Contexto: o usuário JÁ está no app — não precisa convencer a entrar, precisa direcionar o próximo passo da sessão.
- Papel na régua: reforço persistente e não-intrusivo do mote da campanha; o canal que "segura" a mensagem entre pushes/emails sem custo de fadiga de interrupção.
- Segmentar por estado (visto ≠ clicado ≠ convertido); banner de campanha expirada é o pior anti-padrão do canal.

## Email

- **Assunto**: 30–50 caracteres (mobile-first); específico > criativo (Hopkins). **Preheader**: 40–90 caracteres complementando (nunca repetindo) o assunto.
- **Corpo**: 1 ideia, 1 CTA principal (botão, verbo + benefício: "Garantir minha vaga"). Escaneável: título interno, 2–4 blocos curtos, negrito funcional.
- Papel na régua: o canal da história completa — argumento, prova social, detalhe da oferta. Único canal que comporta narrativa.
- Obrigatório: one-click unsubscribe, remetente com nome humano quando o tom pedir.

## SMS

- **160 caracteres = 1 segmento** (acentos podem reduzir para 70 — validar contagem). Ideal: mensagem completa em 1 segmento.
- Estrutura: [Marca]: benefício/urgência + link curto + opt-out ("Sair: responda SAIR" na 1ª mensagem ou conforme regra local).
- Papel na régua: o canal do agora — last call, lembrete D-0, expiração real. Nunca para nutrição.
- Anti-padrão: mais de 2 SMS/semana, link sem contexto, tom corporativo.

## WhatsApp

- Fora da janela de 24h de atendimento: **template aprovado** (categoria marketing) — escrever já no formato de template com variáveis `{{1}}`, `{{2}}`.
- Corpo até ~1024 caracteres, mas o ideal é 2–4 linhas + botões (CTA/quick reply) em vez de link solto.
- Tom conversacional de verdade (é um chat): primeira pessoa, pergunta que convida resposta, sem "email disfarçado".
- Papel na régua: relacionamento e conversão assistida no BR — confirmações, ofertas de alto valor, recuperação com diálogo. Exige opt-in específico do canal.

## DM (redes sociais / inbox da plataforma)

- Curta (2–4 linhas), pessoal, referenciando o contexto real do usuário (interação, compra, evento). Sem bloco promocional colado.
- 1 pergunta ou 1 link, nunca os dois competindo.
- Papel na régua: toque de alto valor percebido para segmentos pequenos (VIPs, reativação premium, convite exclusivo). Volume baixo, personalização alta.

## Orquestração entre canais (mesmo mote, formas diferentes)

- O mote central é um só; cada canal expressa um ÂNGULO dele — nunca a mesma frase copiada nos 6 canais.
- Escalonar, não disparar em bloco: canal principal do toque → aguardar janela (ex. 24h sem conversão) → canal de reforço. Banner in-app pode correr em paralelo por ser passivo.
- Cadeia típica de urgência: email (história completa, D-3) → push (lembrete contextual, D-1) → SMS/WhatsApp (last call, D-0) → banner (persistente durante toda a janela).
- Frequency cap é somado entre canais interruptivos (push + SMS + WhatsApp + DM); banner não conta, email conta com peso menor.
