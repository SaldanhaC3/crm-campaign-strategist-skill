# Entrega Final em HTML — Especificação de UI/UX

Toda entrega de campanha/jornada/régua deve culminar em **um documento HTML visualmente sofisticado**, além do resumo em texto no chat. O HTML é o artefato que o usuário apresenta e compartilha.

## Como entregar (por ambiente)

- **Claude Code / claude.ai com Artifacts**: escrever o arquivo `.html` e publicar via ferramenta Artifact (página privada com URL). Se a ferramenta Artifact não existir, salvar o `.html` no diretório de trabalho e enviá-lo ao usuário (SendUserFile com display render, quando disponível).
- **Outras IAs**: gerar o HTML completo em bloco de código para o usuário salvar.
- Arquivo autocontido: CSS e JS inline, sem CDNs externas, responsivo, tema claro E escuro (`prefers-color-scheme` + suporte a `data-theme`).

## Estrutura obrigatória do documento

1. **Hero/cabeçalho** — nome da campanha, mote/conceito central em destaque, produto, público-alvo, período, objetivo de negócio.
2. **KPIs-alvo** — cards com metas (conversão, lift esperado, receita incremental, MDE do teste). Números grandes, rótulos claros.
3. **Linha do tempo visual da régua** — timeline horizontal (ou vertical no mobile) com cada toque: dia (D-15, D0, D+3…), canal (badge colorido por canal: email/SMS/push/WhatsApp), gatilho e condição de saída. É a peça central do documento.
4. **Cards por toque** — para cada mensagem: canal, timing/gatilho, assunto/mote, corpo resumido, CTA, princípio comportamental usado (tag nomeada: escassez, prova social, loss aversion…), objetivo do toque.
5. **Segmentação e supressões** — quem entra, quem NÃO entra (compradores recentes, do-not-disturbs, fadiga), frequency caps aplicados.
6. **Plano de medição** — holdout (%), métrica primária pré-registrada, MDE, duração, análise intent-to-treat. Scorecard de incrementalidade preenchido (ver `playbook-incrementalidade.md`).
7. **Jornada visual em Mermaid (obrigatória, ao final)** — diagrama da régua/jornada renderizado + painel de edição com o código-fonte, botão de renderizar e de copiar. Seguir `diagramas-mermaid.md`.
8. **Relatório de validação de copy** — tabela por mensagem com os 5 gates (G1–G5) de `pipeline-validacao-copy.md` e ajustes feitos; variantes A/B dos toques de maior alavancagem com hipótese de cada uma.
9. **Racional estratégico + hipóteses** — por que cada decisão foi tomada; aprendizados anteriores aplicados (citar `learnings/`); hipóteses a testar em A/B.

## Padrões de design (UI/UX)

- **Hierarquia**: uma ideia por seção; títulos fortes; o leitor entende a campanha em 30 segundos rolando, e os detalhes em 5 minutos lendo.
- **Cor com função**: uma cor por canal, consistente no documento inteiro; princípios comportamentais como tags discretas; alertas (supressão, cap) em tom de aviso. Nunca decoração sem significado.
- **Tipografia**: fonte de sistema (`system-ui`), corpo ≥16px, contraste AA nos dois temas.
- **Densidade controlada**: cards com respiro; tabelas largas dentro de contêiner com `overflow-x: auto`; nada de parágrafos gigantes — usar listas e destaques.
- **Responsivo**: grid fluido, timeline vira vertical em telas estreitas, `max-width` de leitura ~72ch para texto corrido.
- **Microdetalhes**: badges arredondados para canais, numeração dos toques, ícones simples em SVG inline se agregarem, estados de ênfase no toque de maior alavancagem ("toque de ouro" da régua).
- **Sem dependências externas**: nada de fontes remotas, imagens externas ou bibliotecas via CDN.

## Tom do documento

Documento de estrategista sênior para stakeholder: direto, confiante, com números. Cada seção responde uma pergunta do stakeholder ("o que vamos fazer?", "por quê?", "como saberemos que funcionou?").
