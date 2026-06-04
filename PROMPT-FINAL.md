# Educador Financeiro Inteligente — Desafio Criativo (DIO)

Trilha Santander 2026 - React Frontend  
Moisés | GitHub: sir-devtech

Escolhi o perfil **B** do meu rascunho: quem estuda tech e às vezes ganha um extra, mas não vive só de freela.

Eu tô na DIO focando em React. Tenho entrada mais ou menos fixa (CLT ou ajuda da família, depende do mês) e de vez em quando entra um freela pequeno de dev — aí o total muda e eu não separo direito o que é **investimento em estudo** do que é **gasto de lazer**. No mês passado percebi que delivery + assinatura (streaming, ferramenta) comiam quase **R$ 400** antes do dia 15, e a meta de guardar **R$ 50 por semana** ficou só no papel.

---

## Passo 1 — Papel do Educador Financeiro

Crie a ideia de um Educador Financeiro Inteligente voltado para **quem estuda programação e tem renda mista** — salário ou mesada + freela pontual, sem ser autônomo em tempo integral.

O principal problema dessa pessoa é **misturar gasto com curso, ferramenta e delivery/lazer**, e no fim do mês não saber se sobrou algo pra reserva ou se o freela sumiu em coisa pequena.

A solução deve ajudar o usuário a **separar “caixa estudo” e “caixa pessoal”, ver o mês virando e manter uma meta simples de guardar** (tipo R$ 50/semana), sem planilha chata.

O sistema deve se comunicar de forma **direta, como colega de trilha** — sem palestra de banco e sem culpar por pedir iFood.

---

## Passo 2 — Recursos e experiências inteligentes

O Educador Financeiro Inteligente deve possuir os seguintes recursos:

1. **Painel com duas caixas: Estudo e Pessoal** — curso, certificação, ferramenta de dev de um lado; moradia, transporte, lazer do outro.
2. **Simulação de “mês sem freela”** — e se não entrar o extra? O que cortar primeiro sem prejudicar a trilha.
3. **Alerta “delivery + assinaturas”** — avisa quando passar de um teto que o usuário define (no meu caso começaria em **R$ 350/mês**), porque é onde eu mais escorrego.
4. **Meta semanal de reserva** — acompanhar os **R$ 50/semana** com barra simples e mensagem quando faltar 1–2 depósitos.

A IA deve adaptar as recomendações com base em **quanto entrou de fixo vs freela no mês, quanto foi pra estudo, quanto já foi guardado na meta semanal e se a pessoa está em fase de bootcamp (gastos apertados) ou já estáganando um pouco mais**.

Evite respostas **genéricas, jargão de investimento ou indicação de produto financeiro**. Não prometer rentabilidade.

As sugestões devem ser apresentadas no formato **lista curta, valor em R$ quando couber, um exemplo do meu contexto (estudo + freela) e só um próximo passo**.

---

## Passo 3 — Prompt final

Bloco que eu rodaria no Copilot / ChatGPT:

```text
Atue como um especialista em educação financeira digital.
Crie a proposta de um Educador Financeiro Inteligente para quem estuda programação (bootcamp/trilha tipo DIO) e tem renda mista: entrada fixa ou mesada + freela pontual de dev.

O sistema deve ajudar a separar gastos de estudo (curso, certificação, ferramentas) dos gastos pessoais, simular um mês sem freela extra, e manter uma meta simples de reserva (ex.: R$ 50 por semana).

As principais funcionalidades devem incluir:
- Painel com duas caixas: Estudo e Pessoal
- Simulador "e se não entrar freela este mês?" com cortes priorizados
- Alerta quando delivery + assinaturas passarem de um teto definido pelo usuário
- Acompanhamento de meta semanal de reserva com barra de progresso

A comunicação deve ser direta e de colega, sem julgar gasto com delivery ou streaming.

As respostas devem vir em listas curtas, exemplos em R$, linguagem fácil e um único próximo passo por vez.

Evite jargão bancário, texto vago, promessa de rentabilidade e recomendações que pareçam venda de produto financeiro.

Personalize com base em: fixo vs freela no mês, quanto foi investido em estudo, progresso da meta semanal de reserva e se o usuário está em fase de bootcamp apertada ou com margem maior.

No final, sugira como virar projeto frontend interativo com React e Tailwind: telas, componentes e um detalhe de gamificação (badge, streak, etc).
```

---

## Minhas ideias de frontend (React + Tailwind)

Pensei em algo que **eu** usaria enquanto termino a trilha Santander — não um app genérico de autônomo.

### Ideia 1 — Home “Estudo vs Pessoal”

Dois cards lado a lado: quanto foi pra DIO, cursos e ferramentas; quanto foi pra moradia, comida e lazer. Barra do mês e linha da meta **R$ 50/semana** (4 tick marks).

Componentes: `SplitCard`, `WeeklyGoalBar`, `MonthPicker`.

Badge “Semana no verde” quando bater os R$ 50 — simples, mas eu voltaria pra ver.

### Ideia 2 — “Mês sem freela”

Campo com média do freela dos últimos meses → botão “simular zero freela” → lista: o que é essencial (internet, trilha) vs o que pode pausar (assinatura extra).

`ScenarioButton`, `EssentialTag`, lista com checkbox.

### Ideia 3 — Alerta delivery + assinaturas

Input do teto (default 350). Conforme lança gastos, donut ou barra mostra quanto falta pro teto. Passou? banner amarelo com **uma** sugestão (ex.: “cortar 2 pedidos = volta pro teto”).

`ThresholdInput`, `SpendDonut`, `SoftAlert`.

Tudo com Tailwind, mobile first — é o jeito que tô aprendendo na trilha mesmo.
