# Playbook de Incrementalidade — Desenhar Campanhas com Alta Probabilidade de Lift

Objetivo: toda campanha nasce desenhada para GERAR lift incremental e para PROVAR esse lift. As duas coisas são decisões de design, não de análise posterior.

## Parte 1 — Alavancas que aumentam a probabilidade de lift

Uma campanha só gera lift se muda um comportamento que não aconteceria sozinho. Checklist de design (aplicar ANTES de escrever qualquer copy):

1. **Alvo persuadable**: o segmento escolhido tem gente "em cima do muro"? Champions convertem sozinhos (lift ~zero); lost causes não convertem nunca. Maior densidade de persuadables: engajamento em queda recente, primeira compra sem segunda, carrinho/browse abandonado, trial sem ativação, uso caindo antes da renovação.
2. **Gatilho próximo da intenção**: quanto menor a distância entre o evento de intenção e a mensagem, maior o lift (carrinho 30–60min ≫ newsletter semanal). Se a campanha não tem gatilho comportamental, pergunte se deveria ter.
3. **Informação ou incentivo NOVO**: a mensagem entrega algo que o usuário não tinha (oferta, prazo real, feature que resolve a dor dele, prova social específica)? Relembrar o que ele já sabe gera pouco lift.
4. **Fricção removida no destino**: deep link direto na ação, 1 clique a menos = lift. CTR alto + conversão baixa = problema de Ability, não de mensagem.
5. **Supressão de quem não precisa**: excluir compradores recentes, sure things e do-not-disturbs AUMENTA o lift médio e evita lift negativo (desconto para quem ia comprar = margem queimada).
6. **Incentivo escalonado**: começar sem desconto; incentivo só para quem não respondeu aos toques anteriores. Protege margem e mede o lift do incentivo separado do lift do lembrete.
7. **Timing de fresh start / janela de sobrevivência**: disparar quando a propensão natural a agir é maior (início de mês, pós-pagamento, ponto da curva de churn onde o risco acelera).

## Parte 2 — Desenho do experimento (provar o lift)

Protocolo pré-registro (definir ANTES do envio, nunca depois):

1. **Hipótese e métrica primária** — 1 métrica de decisão (conversão incremental, receita incremental por destinatário), definida antes; o resto é secundário. Escolher métrica depois transforma o teste em exercício de confirmação.
2. **MDE (efeito mínimo detectável)** — o menor lift que mudaria uma decisão de negócio. Se +5% não muda nada, não desenhe o teste para detectar 5%.
3. **Tamanho do holdout** — calcular por MDE, baseline e poder (80%, α=5%). Regras práticas: holdout <10% da audiência raramente tem poder estatístico; bases pequenas ou conversão rara exigem holdouts de 20–50% ou janelas mais longas; réguas perenes podem usar holdout menor (5–10%) acumulando amostra no tempo.
4. **Randomização balanceada** — split aleatório estratificado por RFM/elegibilidade, para que teste e controle sejam comparáveis.
5. **Duração ≥ 1 ciclo completo de compra** — ler resultado cedo produz conclusão que vira do avesso uma semana depois.
6. **Anti-contaminação** — a causa nº 1 de teste inconclusivo: o controle recebe a campanha por outro canal/fluxo. Suprimir o holdout de TODOS os canais da campanha durante a janela.
7. **Análise intent-to-treat** — comparar todos os designados ao tratamento vs todos os do controle (não "quem abriu vs controle" — abrir é auto-seleção e enviesa).
8. **Validade com prazo** — baselines de incrementalidade mudam trimestre a trimestre (fadiga criativa, sazonalidade, concorrência). Re-testar réguas principais a cada 6–12 meses, no máximo.

## Parte 3 — Leitura e decisão

- **Lift = (conv. tratado − conv. controle) / conv. controle**; reportar também o absoluto (conversões incrementais e receita incremental − custo do incentivo).
- Lift ~zero → a campanha antecipa/canibaliza; cortar toque ou mudar segmento.
- Lift negativo em um segmento → do-not-disturbs identificados; criar regra de supressão permanente.
- Lift positivo mas margem negativa (incentivo caro) → testar incentivo menor ou não-monetário.
- Todo resultado alimenta o protocolo de `medicao-e-aprendizado.md` (só vira regra após repetir 2x ou vir de teste com controle).

## Scorecard pré-lançamento

Antes de aprovar qualquer campanha, pontuar 0–2 em cada item (alvo persuadable, gatilho de intenção, novidade real, fricção removida, supressões aplicadas, holdout desenhado, métrica pré-registrada). **< 10/14 → redesenhar antes de enviar.** Incluir o scorecard preenchido na entrega.
