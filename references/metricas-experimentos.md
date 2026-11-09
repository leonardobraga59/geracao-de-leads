# Métricas e experimentos

Abra este arquivo quando o plano precisar de números (definições, custo, CAC, conversão) ou de um teste com critério de decisão definido antes de começar.

Nota: o conteúdo deste arquivo é adaptação operacional desta skill. Não vem do livro nem do curso, e não deve ser atribuído a eles.

---

## 1. Definições que acompanham todo número

Toda métrica declara cinco coisas: numerador, denominador, coorte, janela e deduplicação. Sem isso, dois números com o mesmo nome não são comparáveis.

- Coorte: o grupo de pessoas que entrou na mesma etapa no mesmo período (por exemplo, quem virou lead engajado na semana de 3 a 9).
- Janela: o prazo em que se observa o avanço da coorte. Deve ser compatível com o ciclo de venda.
- Deduplicação: a mesma pessoa conta uma vez por métrica, mesmo que apareça em mais de um canal, formulário ou campanha.

| Métrica | Definição | Numerador | Denominador | Deduplicação |
|---|---|---|---|---|
| Lead engajado | Pessoa contatável que demonstrou interesse, com o evento definido de antemão | Pessoas únicas que fizeram o evento (cadastro, resposta, pedido do material) | Pessoas únicas alcançadas, ou nenhum se for contagem absoluta | Por pessoa, não por cadastro |
| Lead qualificado | Aderência e intenção suficientes para o próximo passo da oferta, pelas regras de [qualificacao-sdr.md](./qualificacao-sdr.md) | Pessoas únicas que cumpriram as regras | Leads engajados da coorte | Por pessoa |
| Reunião agendada | Reunião confirmada no sistema ou pelo responsável | Pessoas únicas com confirmação | Leads qualificados encaminhados ao SDR na coorte | Uma por pessoa; reagendamento não cria outra |
| Reunião realizada | Conversa que de fato aconteceu, separada de agendamento | Pessoas únicas que compareceram | Reuniões agendadas da coorte | Por pessoa |
| Cliente pagante | Primeiro pagamento confirmado | Pessoas únicas com primeiro pagamento confirmado na janela | A etapa anterior da coorte (reunião realizada, ou lead qualificado em oferta direta) | Por pessoa, não por transação |

Política para pagamento (decida e escreva antes de contar):
- Estorno dentro do prazo de reembolso: o cliente sai da contagem de pagantes daquela coorte. Registre quantos saíram.
- Pagamento duplicado ou reenviado: conta um cliente.
- Falha de cobrança sem confirmação: não é pagante.
- Cliente que volta depois de cancelar: não entra como novo cliente de aquisição; vale como reativação (ver seção 5).

### Pessoas únicas e tentativas

Separe sempre as duas contagens.
- Tentativas: mensagens enviadas, ligações feitas, anúncios entregues, e-mails disparados. Medem esforço.
- Pessoas únicas: quantas pessoas diferentes foram alcançadas e responderam. Medem resultado.

Cem mensagens para quarenta pessoas são cem tentativas e quarenta pessoas únicas. Taxa de resposta se calcula sobre pessoas únicas contatáveis, salvo quando o plano pedir expressamente taxa por tentativa.

---

## 2. Fórmulas

**Custo por lead qualificado** = custo atribuível à aquisição ÷ leads qualificados únicos, na mesma coorte e janela.

**CAC completo** = (mídia + trabalho comercial e de marketing alocado + ferramentas atribuíveis + comissões atribuíveis) ÷ novos clientes pagantes únicos, na mesma janela.

- Trabalho alocado: horas × custo da hora, pelas pessoas que de fato atuaram na aquisição daquela coorte.
- Ferramentas: só a fração usada na aquisição, pelo critério de alocação escolhido.
- Não conte o mesmo custo duas vezes. Se a hora de uma pessoa já entrou no trabalho comercial, não entra de novo na ferramenta ou na comissão.
- Declare o critério de alocação (por horas, por volume de leads, por campanha) e use o mesmo nas comparações.

**Conversão por etapa** = pessoas que avançaram ÷ pessoas elegíveis na etapa anterior, na mesma coorte e janela.

- Se o denominador for zero, o resultado é "não calculável". Não escreva zero, nem infinito, nem um valor estimado.
- Sem nenhum cliente pagante, o CAC é "não calculável"; o gasto até ali é custo acumulado, não CAC igual a zero.

### Assinatura

Para assinatura, compare o CAC com a contribuição observada por coorte e horizonte. Contribuição é a receita menos os custos diretos de atender, por cliente da coorte, até o horizonte medido (por exemplo, 3 ou 6 meses).

- Use a permanência observada da coorte. Não suponha retenção ilimitada.
- Se a coorte é nova e ainda não tem horizonte, diga que o retorno é desconhecido e trate qualquer projeção como hipótese rotulada.
- A razão de 3 para 1 entre valor do cliente e CAC é uma referência contextual. Não garante viabilidade, e não substitui a conta do próprio negócio.

---

## 3. Ficha obrigatória por teste

Todo experimento tem esta ficha preenchida antes de começar. Campo sem resposta vira "pendente" e dado pendente que muda a decisão precisa ser resolvido antes de iniciar.

| Campo | O que preencher |
|---|---|
| Hipótese e público | Qual mudança deve produzir qual resultado, e para quem |
| Oferta e canal | O que a pessoa receberá, como chegará até isso e qual será o CTA |
| Execução | Responsável, início, prazo, capacidade semanal e dependências |
| Custo e volume | Teto de gasto e de horas; pessoas únicas e número de tentativas, separados |
| Medição | Evento principal, métricas de qualidade, janela de atribuição e origem dos dados |
| Decisão | Quando continuar, ajustar, parar ou considerar o resultado inconclusivo |

Na linha de decisão, escreva os limites antes do teste, em termos observáveis. Exemplo de formato: "continuar se o custo por lead qualificado ficar abaixo de X com pelo menos N pessoas únicas; parar se Y; inconclusivo se a amostra ficar abaixo de N ou o ciclo de venda não tiver fechado".

### Calendário não é evidência

Uma revisão semanal organiza o trabalho. Ela não torna um resultado conclusivo.

- Amostra insuficiente, ou ciclo comercial que ainda não terminou: o resultado é "inconclusivo".
- Não declare vencedor porque a semana acabou, nem fracasso do canal por falta de vendas numa amostra pequena.
- Dois cadastros e nenhuma venda não provam nada. Registre a observação e decida o que fazer para ter amostra (mais tempo, mais volume, outro público) ou pare por motivo operacional declarado.
- Interromper antes do prazo é legítimo quando há problema operacional ou evidência clara de baixa aderência. Registre o motivo.

### Exemplo de teste inicial (hipótese ilustrativa)

Dados fictícios, só para mostrar o preenchimento.

| Campo | Exemplo |
|---|---|
| Hipótese e público | Um diagnóstico ligado ao produto atrai interessados mais aderentes que um material genérico. Público: pequenas clínicas que já usam planilha para agenda |
| Oferta e canal | Versão A: checklist genérico. Versão B: diagnóstico de 10 perguntas com resultado imediato. Canal: uma página, com tráfego de uma só origem. CTA: "Ver meu resultado" |
| Execução | Responsável: a pessoa de marketing. Início: segunda-feira. Prazo: a definir pelo tráfego disponível, com a janela de venda incluída. Dependência: página das duas versões pronta |
| Custo e volume | Teto de gasto e de horas: a definir com quem decide a verba. Públicos e condições semelhantes nas duas versões |
| Medição | Evento principal: cadastro. Qualidade: lead qualificado pelas regras do projeto. Desfecho: cliente pagante dentro da janela. Dados: formulário e CRM |
| Decisão | Continuar com B se tiver mais qualificados por pessoa única e custo por qualificado igual ou menor, com amostra mínima combinada antes. Inconclusivo se a amostra for menor ou se nenhum lead tiver chegado ao fim do ciclo de venda |

Prazo, orçamento e amostra saem do tráfego disponível, não de uma regra fixa. Meça qualificados e vendas, além do custo por cadastro.

---

## 4. Ordem para ler os números

1. Os dados estão completos para a coorte e a janela?
2. Pessoas únicas e tentativas foram separadas?
3. Há amostra suficiente e o ciclo de venda terminou? Se não, "inconclusivo".
4. Qualidade (qualificados, comparecimento, vendas) antes de volume (cadastros).
5. Custo total (CAC completo) antes de custo de mídia isolado.
6. Só então ampliar, ajustar ou parar.

---

## 5. Indicação: projeção e conferência

Indicação só vira crescimento depois da conversão. A proporção de clientes que indicam não é a proporção de novos clientes, e não se compara direto com a de cancelamento.

Projeção para uma janela:

- Novos clientes por indicação = base inicial × proporção que indica × média de indicados por indicador × conversão dos indicados.
- Base final = base inicial + novos clientes únicos de todos os canais + reativações − clientes perdidos, na mesma janela.

Exemplo hipotético: base de 100 clientes, 10% indicam, cada indicador indica 1 pessoa, 20% dos indicados compram.
- 100 × 10% × 1 × 20% = 2 novos clientes.
- Com 5 cancelamentos e nenhum outro movimento, a base final é 100 + 2 − 5 = 97.

Cuidados:
- A projeção depende de hipóteses declaradas (proporção, média de indicados, conversão). Mostre-as junto do resultado.
- Conte cada cliente novo uma vez, mesmo que tenha chegado por dois canais.
- A janela de conversão deve caber no ciclo de venda: uma indicação deste mês pode converter depois.
- Prefira as aquisições efetivas registradas no CRM. A fórmula serve como projeção, não como medida.
