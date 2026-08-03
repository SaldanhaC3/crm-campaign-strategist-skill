# Medição, Incrementalidade e Protocolo de Aprendizado

## Medindo o que importa

Hierarquia de métricas (nunca otimizar só o topo):
1. **Entrega**: bounce (<2%), spam complaint (<0,1%).
2. **Atenção**: open rate (direcional — iOS privacy infla), CTR.
3. **Ação**: conversão por destinatário, receita por destinatário (RPR).
4. **Incremental**: lift vs grupo de controle — a única métrica que prova que a campanha causou o resultado.
5. **Saúde de base**: unsubscribe, fadiga, LTV do segmento.

## Holdout / grupo de controle

- Toda régua permanente e toda campanha relevante: reservar 5–10% do público-alvo que NÃO recebe a mensagem.
- Lift incremental = (conversão do grupo tratado − conversão do controle) / conversão do controle.
- Se o lift é ~zero, a campanha só antecipa/canibaliza conversões orgânicas — cortar ou reformular.
- Controle por segmento (um holdout dentro de cada segmento RFM), senão o resultado confunde segmentação com efeito da mensagem.
- Rodar experimento contínuo: todo mês, estimativa de lift atualizada por régua.

## A/B testing

- 1 variável por teste (assunto OU horário OU canal OU oferta).
- Tamanho mínimo: calcular por MDE; regra prática, não declarar vencedor com <1.000 destinatários por braço ou antes do ciclo completo de conversão.
- Testar em ordem de alavancagem: oferta/incentivo > timing/gatilho > canal > assunto > copy do corpo > design.

## Protocolo de aprendizado contínuo (quando o usuário envia resultados)

Ao receber slides, apresentações, tabelas ou dashboards de resultados de campanha:

1. **Extrair** para cada campanha: produto, segmento/público, canal, tipo de régua, timing, mote/oferta, métricas (open, CTR, conversão, receita, unsubscribe, lift se houver).
2. **Comparar** contra: (a) benchmark interno anterior do mesmo produto/segmento; (b) benchmarks de `canais-e-benchmarks.md`.
3. **Diagnosticar** com o modelo Fogg: abertura baixa → problema de prompt (assunto/canal/horário); CTR baixo → motivação (oferta/mote); conversão pós-clique baixa → ability (fricção no destino).
4. **Registrar** em `learnings/<produto-ou-segmento>.md` no diretório de trabalho, formato:

```markdown
## <data> — <campanha>
- Contexto: produto, público, canal, régua, mote
- Resultado: métricas-chave vs benchmark
- Insight: o que funcionou/falhou e a causa provável
- Aplicar na próxima: regra concreta (ex.: "SMS D-1 converteu 3x email → SMS vira canal padrão de last call neste público")
```

5. **Aplicar**: em toda nova campanha do mesmo produto/segmento/público, ler `learnings/` primeiro e citar explicitamente quais aprendizados moldaram a nova estratégia.

Regra: um resultado só vira "regra" após se repetir 2x ou vir de teste com controle; antes disso é hipótese a re-testar.
