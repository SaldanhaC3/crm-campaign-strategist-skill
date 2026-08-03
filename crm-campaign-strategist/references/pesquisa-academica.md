# Pesquisa Acadêmica Open-Access — Retenção, Churn e Targeting

Achados de papers revisados/open-access que mudam decisões práticas de campanha.

## Uplift modeling: em quem mirar a retenção

Fontes: [benchmark Orange Belgium (arXiv 2312.07206)](https://arxiv.org/html/2312.07206v1), [Devriendt et al., Information Sciences](https://www.sciencedirect.com/science/article/pii/S0020025519312022), [uplift B2B (Industrial Marketing Management)](https://www.sciencedirect.com/science/article/am/pii/S0019850121001930).

A pergunta certa não é "quem vai churnar?" e sim "quem muda de comportamento SE eu mandar a mensagem?". Quatro grupos:

| Grupo | Comportamento | Ação |
|---|---|---|
| **Sure things** (~93% em telecom) | fica de qualquer jeito | não gastar oferta/mensagem |
| **Lost causes** | sai de qualquer jeito | não gastar |
| **Persuadables** (~3–4%) | fica SÓ se contatado | **o único alvo que gera lift** |
| **Do-not-disturbs** (~3%) | a mensagem PIORA o resultado (lembra de cancelar) | suprimir ativamente |

Implicações práticas:
- Mirar os "maiores riscos de churn" desperdiça oferta em lost causes e pode ATIVAR do-not-disturbs — campanha de retenção pode ter lift negativo em parte da base.
- O grupo do-not-disturb é a prova científica de que "não mandar" é uma decisão estratégica válida — reforça dias de descanso e supressão.
- Sem infraestrutura de uplift, a aproximação prática é: holdout sempre + começar por risco médio/engajamento em queda (onde há mais persuadables) e medir lift por segmento.
- Nota de honestidade do benchmark: modelos preditivos simples às vezes superam uplift models — sofisticação de modelo não substitui experimento bem desenhado.

## Personalização — experimentos de campo

- Experimento com milhões de envios: nome no assunto → +20% abertura, +31% leads, −17% unsubscribe ([Sahni et al.](https://www.researchgate.net/publication/323439461_Personalization_in_Email_Marketing_The_Role_of_Noninformative_Advertising_Content)).
- Personalização correlaciona significativamente com redução de churn em e-commerce (p=0,004, 2024).
- RCT em app financeiro (2025): mensagens agênticas/adaptativas vs régua fixa — efeitos em unsubscribe e tempo até conversão ([arXiv 2512.17462](https://arxiv.org/pdf/2512.17462)).
- Hierarquia validada: personalização comportamental (o que fez) > por atributo (quem é) > cosmética (nome). A cosmética já dá lift; a comportamental é onde estão os 6x de transação.
- Framework de experimentação contínua para personalização: [Personalization and targeting: how to experiment, learn & optimize (ScienceDirect, 2025)](https://www.sciencedirect.com/science/article/pii/S016781162500062X).

## Churn analytics e sobrevivência

- Abordagem integrada moderna: predição de churn + explicabilidade (SHAP) + análise de sobrevivência + segmentação para retenção personalizada ([arXiv 2510.11604](https://arxiv.org/html/2510.11604v1)).
- Uso prático: análise de sobrevivência dá a JANELA de intervenção (quando o risco acelera) — é ela que deve definir o gatilho da régua "em risco", não um número fixo de dias copiado de benchmark.
- Lembretes de assinatura reduzem churn involuntário em 20–35%; réguas de dunning (falha de pagamento) são a retenção de maior ROI porque o cliente nem decidiu sair.

## Regras derivadas para a skill

1. Toda campanha de retenção mira persuadables, não "maior risco" — e mede lift com holdout por segmento.
2. Supressão (do-not-disturb, sunset de inativos) é decisão estratégica de primeira classe, não falta de campanha.
3. Janela de gatilho de churn vem dos dados de sobrevivência do próprio produto quando disponíveis.
4. Resultado de modelo/benchmark nunca substitui experimento controlado — padrão-ouro é o RCT interno.
