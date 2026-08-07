# Pipeline de Validação de Copy — Orquestração Antes da Entrega

Nenhum texto vai para a entrega final sem atravessar os 5 gates abaixo, NESTA ordem. Cada gate reprova ou aprova; texto reprovado volta, é reescrito e re-validado. A entrega final inclui o resultado da validação (tabela de gates por mensagem).

## Fluxo

```
Rascunho → G1 Formato → G2 Estratégia → G3 Persuasão → G4 Compliance → G5 Orquestração → Entrega (HTML)
```

## G1 — Formato do canal (objetivo, binário)

Para cada mensagem, validar contra `canais-copy-specs.md`:
- [ ] Dentro do limite de caracteres do canal (CONTAR de fato: título de push ≤35, SMS ≤160/segmento, headline de banner ≤40, assunto ≤50…).
- [ ] Exatamente 1 CTA principal; CTA é verbo no imperativo.
- [ ] Deep link/destino correto para a ação do toque (não homepage genérica).
- [ ] Variáveis de personalização com fallback definido (`{{nome|você}}` — nunca "Olá , ").
- [ ] WhatsApp fora da janela de 24h está em formato de template com variáveis.

## G2 — Estratégia (o texto serve ao toque?)

- [ ] A mensagem cumpre o objetivo declarado DESTE toque na régua (ativação ≠ conversão ≠ lembrete).
- [ ] Entrega informação ou incentivo NOVO (alavanca de lift — relembrar o que o usuário já sabe gera pouco lift).
- [ ] Específica no estilo Hopkins: números, fatos, prazos reais ("25% até sexta" e não "condições especiais").
- [ ] Coerente com o mote central da campanha (mesmo conceito, ângulo próprio do canal).
- [ ] Se há aprendizado registrado em `learnings/` para este produto/segmento, foi aplicado (citar qual).

## G3 — Persuasão (psicologia auditável)

- [ ] Princípio comportamental nomeado e corretamente aplicado (escassez só se real; prova social com número específico; loss aversion só sobre perda concreta do usuário).
- [ ] Teste Fogg: no momento do disparo, o usuário tem motivação (o texto a cria?) e habilidade (a ação é 1 clique?); o prompt chega perto da intenção?
- [ ] Teste "Obvious Adams": a relevância é óbvia em 2 segundos para quem recebe?
- [ ] Sem exagero que quebra confiança (superlativo vazio, urgência falsa, "última chance" pela terceira vez).

## G4 — Compliance e deliverability

- [ ] Opt-out presente onde obrigatório (email: one-click unsub; SMS: instrução de saída; WhatsApp: template aprovado + opt-in do canal).
- [ ] Sem gatilhos clássicos de spam no assunto (CAIXA ALTA, !!!, "grátis" repetido, cifrão em excesso).
- [ ] Promessa da mensagem = realidade da landing (mismatch gera complaint, e complaint >0,1% mata o canal).
- [ ] LGPD: o segmento tem base legal/opt-in para ESTE canal.

## G5 — Orquestração (o conjunto, não a peça)

- [ ] Frequency cap somado dos canais interruptivos respeitado no período (ver `reguas-e-timings.md`); dias de descanso preservados.
- [ ] Nenhuma frase idêntica copiada entre canais; escalonamento definido (principal → reforço → last call; banner em paralelo).
- [ ] Condições de saída suprimem o usuário de TODOS os canais restantes ao converter.
- [ ] Colisão com outras réguas ativas verificada (usuário em onboarding + carrinho + campanha = priorizar por valor).
- [ ] Scorecard de incrementalidade da campanha ≥10/14 (`playbook-incrementalidade.md`).

## Formato do relatório de validação (vai na entrega HTML)

Tabela por mensagem: toque | canal | G1–G5 (✓/✗ com nota do ajuste feito) | versão final. Reprovações corrigidas devem ser mencionadas — mostram o rigor do processo, não fraqueza.

## Variantes A/B

Para os 1–2 toques de maior alavancagem da régua, entregar 2 variantes de copy que testem UMA variável (ângulo do mote OU princípio de persuasão OU formato do CTA), com a hipótese explícita de cada variante.
