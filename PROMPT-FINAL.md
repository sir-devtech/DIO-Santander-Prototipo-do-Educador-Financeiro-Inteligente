# Educador Financeiro Inteligente — Desafio Criativo (DIO)

Trilha Santander 2026 - React Frontend  
Moisés | GitHub: sir-devtech

Fiz esse desafio pensando em quem trabalha por conta e nunca sabe se o mês vai fechar bem. Conheço gente (e já passei perto disso) que ganha bem num mês e no outro aperta — e a planilha acaba ficando de lado.

---

## Passo 1 — Papel do Educador Financeiro

Crie a ideia de um Educador Financeiro Inteligente voltado para **freelancers e autônomos que ganham valores diferentes a cada mês**.

O principal problema dessa pessoa é **não ter clareza de quanto pode gastar, quanto guardar e quanto separar pra imposto** quando a renda não é fixa. No fim das contas vira chute e ansiedade.

A solução deve ajudar o usuário a **ver pra onde o dinheiro foi, planejar um mês mais fraco e montar uma reserva aos poucos**, sem aquela planilha gigante que ninguém mantém.

O sistema deve se comunicar de forma **simples, direta e sem frescura** — nada de parecer que tá julgando se a pessoa gastou errado.

---

## Passo 2 — Recursos e experiências inteligentes

O Educador Financeiro Inteligente deve possuir os seguintes recursos:

1. **Um painel básico de entradas e saídas** — o usuário vê fixo, variável, quanto sobrou e uma sugestão de % pra reserva e imposto.
2. **Simulação de “mês ruim”** — tipo: “e se eu ganhar 30% menos?” e a ferramenta sugere o que cortar primeiro.
3. **Lições curtas** — reserva de emergência, separar conta pessoal do trabalho, noção de DAS/imposto, cada uma em poucos minutos.

A IA deve adaptar as recomendações com base em **quanto a pessoa ganhou em média nos últimos 3 meses, quanto já guardou, a meta dela (tipo guardar 3 ou 6 meses de custo) e se prefere ir com calma ou um pouco mais ousado no corte de gastos**.

Evite respostas **muito genéricas, cheias de termo de banco ou parecendo propaganda de investimento**. Não prometer lucro nem indicar produto X ou Y.

As sugestões devem ser apresentadas no formato **lista curta, valor em real quando fizer sentido, exemplo do dia a dia e só uma ação pra fazer agora**.

---

## Passo 3 — Prompt final

É esse bloco aqui que eu usaria no Copilot / ChatGPT:

```text
Atue como um especialista em educação financeira digital.
Crie a proposta de um Educador Financeiro Inteligente para freelancers e autônomos com renda que muda de um mês pro outro.

O sistema deve ajudar a pessoa a organizar gastos e ganhos, simular um mês com menos entrada, separar uma parte pra imposto e reserva, e aprender o básico de finanças sem depender de planilha complexa.

As principais funcionalidades devem incluir:
- Painel simples com categorias: fixo, variável, reserva e impostos
- Simulador do tipo "e se eu ganhar X% a menos?" com ideia do que cortar primeiro
- Trilha de micro-aulas sobre reserva, conta pessoal vs trabalho e noções de imposto pra autônomo

A comunicação deve ser direta e amigável, como quem já passou por mês apertado e quer ajudar de verdade.

As respostas devem vir em listas curtas, com exemplos em R$ quando couber, linguagem fácil e só um "próximo passo" por vez.

Evite jargão de banco, texto vago, promessa de rentabilidade e qualquer coisa que pareça consultoria ou venda de produto financeiro.

Use como base pra personalizar: média dos últimos 3 meses, quanto já foi guardado, meta de reserva (3 ou 6 meses de custo fixo) e se o perfil é mais conservador ou moderado.

No final, me dê ideias de como virar um projeto frontend interativo com React e Tailwind: telas principais, componentes que fariam sentido e alguma forma de deixar o uso mais engajador (badge, barra de progresso, etc).
```

---

## Minhas ideias de frontend (React + Tailwind)

Depois de montar o prompt, fui rabiscando como isso poderia virar tela. São 3 caminhos — não precisa ser os três no mesmo app, é mais pra explorar:

### Ideia 1 — Tela inicial “quatro caixinhas”

Na home mostraria: quanto entrou no mês, gastos fixos, o que sobrou e quanto já foi pra reserva/imposto. Barra colorida: verde ok, amarelo atenção, vermelho apertado.

Componentes que eu criaria: card de resumo, lista de categorias, seletor de mês.

Se bater a meta do mês, aparece um selo tipo “mês no azul” — bobo, mas dá vontade de voltar.

### Ideia 2 — Simulador com slider

O usuário informa uma média de ganho e arrasta um slider pra baixo (ex.: -20%, -40%). A lista mostra cortes sugeridos e ele marca o que topa fazer.

Daria pra usar um componente de slider, linha de sugestão com tag de prioridade (essencial / pode esperar).

A barra de “saúde do caixa” ia mudando na hora — feedback visual ajuda quem não gosta de número solto.

### Ideia 3 — Trilha rápida de estudo

Cards com lição de 2–3 min, uma pergunta no fim, depois volta pro painel. Módulos desbloqueiam aos poucos: reserva, imposto, separar PF e PJ.

Streak de dias seguidos abrindo o app — bem estilo app de hábito, mas pro lado educação financeira.

---

Fim do arquivo. Qualquer dúvida na correção, o essencial tá nos três passos + o bloco do Passo 3 em `text` acima.
