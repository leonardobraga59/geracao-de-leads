# geracao-de-leads

Skill para o Claude que gera e prioriza ideias de captação de lead pelo método do $100M Leads, de Alex Hormozi. Funciona no Claude Code, no Claude Desktop e no claude.ai. Em português do Brasil.

## O que ela faz

- Junta o contexto do seu projeto antes de propor qualquer coisa, separando fato, hipótese e o que falta, e pergunta só o que muda a decisão.
- Diagnostica onde está o gargalo (volume, qualidade, conversão, entrega ou economia) em vez de supor que todo problema pede mais lead.
- Escolhe o canal e o material gratuito ligados à oferta, define como qualificar cada lead e para onde ele vai (oferta direta, nutrição, SDR ou encerramento).
- Transforma a ideia principal num experimento com hipótese, prazo, custo máximo, volume, métricas e critério de decisão.

A entrega sai sempre no mesmo formato, com diagnóstico curto, tabela de ideias (canal, público, material ou oferta, próximo passo e esforço), ficha do experimento prioritário, regras de qualificação e encaminhamento, métricas, dúvidas e fontes do contexto.

O Claude abre só a referência de que precisa.

| Arquivo | Assunto |
|---|---|
| `references/fundamentos.md` | Lead engajado, Core Four, ímã de lead, regra dos 100, aberto até a meta, mais melhor novo, rota de crescimento |
| `references/contato-um-a-um.md` | Contato quente, os primeiros 5 clientes, contato frio e abordagem transparente |
| `references/um-para-muitos.md` | Conteúdo gratuito e anúncio pago |
| `references/quem-traz-lead.md` | Indicação, funcionários, agências e afiliados |
| `references/aplicar-num-projeto.md` | Os oito passos para usar o método num projeto real |
| `references/qualificacao-sdr.md` | Sinais de oportunidade, os quatro destinos do lead, perguntas consultivas e o registro para o SDR |
| `references/metricas-experimentos.md` | Definições, fórmulas de custo e conversão, a ficha de teste e os critérios de decisão |

O arquivo `evals/casos.md` traz dez casos de teste com os critérios de aceitação, para quem for manter a skill. Ele não é lido no atendimento.

## Limites

A skill planeja e não executa. Ela não publica post, não manda mensagem, não cria anúncio, não marca reunião e não conecta CRM, WhatsApp ou agenda. Toda abordagem que ela sugere diz quem está falando e por quê, nunca inventa indicação ou relação, e para quando a pessoa pede.

## Instalar

**Pelo skills CLI**, que instala no Claude Code e em outros agentes

```bash
npx skills add leonardobraga59/geracao-de-leads
```

**No Claude Code, à mão**

```bash
git clone https://github.com/leonardobraga59/geracao-de-leads ~/.claude/skills/geracao-de-leads
```

Para atualizar depois, `git -C ~/.claude/skills/geracao-de-leads pull`. No Claude Desktop, na aba Code, dá para pedir ao próprio Claude "instala a skill https://github.com/leonardobraga59/geracao-de-leads na minha pasta de skills".

**No claude.ai e no chat do Claude Desktop**

Baixe o `geracao-de-leads.zip` na página de [releases](https://github.com/leonardobraga59/geracao-de-leads/releases) e envie o arquivo nas configurações do Claude, na seção de Skills. A execução de código precisa estar ligada.

## Como usar

Peça do jeito normal, sem citar a skill. Por exemplo "me dá ideias de captação de lead para a minha clínica" ou "como consigo os primeiros cinco clientes desse serviço". O Claude abre a skill sozinho, faz as perguntas de contexto que faltarem e devolve as ideias priorizadas.

## Aviso

Resumo independente e não oficial, escrito com outras palavras a partir do livro $100M Leads e do curso gratuito $100M Leads Course. Não tem ligação com Alex Hormozi nem com a Acquisition.com e não substitui o livro. Os números e as taxas citados são do autor, em dólar e no mercado americano, e servem como hipótese a medir, não como promessa de resultado. A qualificação, o encaminhamento ao SDR, as métricas, os experimentos e as correções de conta são adaptações desta skill, marcadas como tal nos arquivos, e não vêm do livro nem do curso.
