# CRM Campaign Strategist — Skill

Skill de IA (formato [Claude Skills](https://www.anthropic.com/news/skills)) que transforma um assistente de IA em um **estrategista master de CRM e lifecycle marketing**: jornadas, réguas, campanhas ad hoc, onboarding, carrinho abandonado, win-back e contagens regressivas de evento — com timing, canal, mote e plano de medição definidos, com base em um arcabouço teórico estudado e documentado (não um prompt genérico).

## O que vem incluído

```
crm-campaign-strategist/
├── SKILL.md                              # instruções principais + fluxo de trabalho + regras de ouro
└── references/
    ├── fundamentos.md                    # estágios de lifecycle, jornada vs régua vs ad hoc, RFM
    ├── reguas-e-timings.md               # templates de timing: onboarding, carrinho, win-back, countdown D-15→D+30
    ├── canais-e-benchmarks.md            # benchmarks 2025-2026 de email/SMS/push/WhatsApp-RCS
    ├── psicologia-comportamental.md      # Fogg (B=MAT), Cialdini, Hooked, vieses cognitivos
    ├── medicao-e-aprendizado.md          # holdout groups, incrementalidade, A/B, aprendizado contínuo
    ├── classicos-dominio-publico.md      # Claude Hopkins, Walter Dill Scott, Obvious Adams
    ├── pesquisa-academica.md             # uplift modeling, papers open-access sobre churn/retenção
    ├── playbook-incrementalidade.md      # alavancas de lift + protocolo de experimento (MDE, holdout, ITT) + scorecard
    ├── entrega-html.md                   # spec do documento HTML final (UI/UX, timeline visual da régua)
    ├── compliance-e-deliverability.md    # Gmail/Yahoo 2026, spam rate, one-click unsub, LGPD
    ├── canais-copy-specs.md              # formatos e papel de cada canal: push, banner in-app, email, SMS, WhatsApp, DM
    └── pipeline-validacao-copy.md        # 5 gates de validação de copy antes da entrega
```

Diferenciais: toda campanha passa por um **scorecard de incrementalidade** (7 alavancas de lift, mínimo 10/14 para aprovar) e é entregue como **documento HTML sofisticado** (hero com mote, KPIs-alvo, timeline visual da régua, plano de medição com holdout), além do resumo em texto.

A skill lê os arquivos de `references/` sob demanda conforme o tipo de tarefa — isso mantém o contexto principal enxuto e permite profundidade real sem sobrecarregar cada resposta.

## Como usar

### Claude Code / Claude Agent SDK

1. Baixe este repositório.
2. Copie a pasta `crm-campaign-strategist/` para dentro de `.claude/skills/` do seu projeto (ou para `~/.claude/skills/` para disponibilizar em todos os projetos).
3. No Claude Code, a skill é carregada automaticamente e disparada quando você pede algo relacionado a CRM/jornadas/réguas, ou explicitamente com `/crm-campaign-strategist`.

```bash
git clone https://github.com/<seu-usuario>/crm-campaign-strategist-skill.git
mkdir -p .claude/skills
cp -r crm-campaign-strategist-skill/crm-campaign-strategist .claude/skills/
```

### Claude.ai (projetos/Skills nativas)

Se sua conta tiver suporte a Skills customizadas, faça upload da pasta `crm-campaign-strategist/` (ou compacte em `.zip`) na configuração de Skills do projeto.

### Qualquer outra IA (ChatGPT, Gemini, LLM local, etc.)

O formato é apenas Markdown puro — funciona como base de conhecimento em qualquer ferramenta que aceite arquivos de contexto/system prompt:

1. Anexe `SKILL.md` como instrução de sistema/persona.
2. Anexe os arquivos de `references/` relevantes para a tarefa (ou todos, se o limite de contexto permitir) como conhecimento adicional.
3. Peça a campanha, régua ou jornada desejada.

## Exemplo de uso

> "Crie a régua completa de um webinar em 20/09, do anúncio ao pós-evento, com canais e motes."

> "Aqui está a tabela de resultados da última campanha de carrinho abandonado (anexo). O que aprendemos e como aplicamos na próxima?"

## Filosofia da skill

- Dados do cliente sempre vencem benchmark de mercado.
- Toda régua tem condição de saída e respeita frequency cap cross-channel.
- Toda campanha relevante roda com grupo de controle (holdout) para medir lift incremental.
- Retenção mira "persuadables" (uplift modeling), não simplesmente quem tem maior risco de churn.
- Motes ancoram em princípios comportamentais nomeados, não em achismo criativo.
- Aprendizado contínuo: resultados enviados pelo usuário viram regras aplicadas nas próximas campanhas do mesmo produto/segmento.

## Licença

MIT — use, modifique e redistribua livremente. Veja [LICENSE](LICENSE).

## Contribuindo

Sugestões de novos benchmarks, papers ou princípios são bem-vindas via issue ou pull request.
