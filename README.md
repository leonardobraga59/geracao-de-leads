# geracao-de-leads

Skill para o Claude que gera e prioriza ideias de captação de lead pelo método do $100M Leads, de Alex Hormozi. Funciona no Claude Code, no Claude Desktop e no claude.ai. Em português do Brasil.

## O que ela faz

- Junta o contexto do seu projeto antes de propor qualquer coisa, a partir do que você contou, dos arquivos do projeto e de perguntas de contexto.
- Diagnostica o estágio do negócio e a restrição, escolhe os canais (os quatro métodos do Core Four e quem traz lead por você) e decide entre fazer mais, melhor ou algo novo.
- Gera ideias por canal e entrega uma tabela com canal, ideia, ímã ou oferta, público, primeiro passo, métrica e esforço.

O método fica em cinco arquivos de referência, com passo a passo, números, erros comuns e perguntas que viram ideias.

| Arquivo | Assunto |
|---|---|
| `references/fundamentos.md` | Lead engajado, Core Four, ímã de lead, regra dos 100, aberto até a meta, mais melhor novo, rota de crescimento |
| `references/contato-um-a-um.md` | Contato quente, os primeiros 5 clientes e contato frio |
| `references/um-para-muitos.md` | Conteúdo gratuito e anúncio pago |
| `references/quem-traz-lead.md` | Indicação, funcionários, agências e afiliados |
| `references/aplicar-num-projeto.md` | Os sete passos para usar o método num projeto real e o formato da saída |

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

Resumo independente e não oficial, escrito com outras palavras a partir do livro $100M Leads e do curso gratuito $100M Leads Course. Não tem ligação com Alex Hormozi nem com a Acquisition.com e não substitui o livro. Os números e as taxas citados são do autor, em dólar e no mercado americano, e servem como hipótese a medir, não como promessa de resultado.
