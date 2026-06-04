# Educador Financeiro Inteligente — Desafio Criativo (DIO)

Trilha Santander 2026 - React Frontend  
Moisés Santos | GitHub: sir-devtech | Sir Tech Solutions

Montei esse desafio a partir do **meu** contexto, não de um perfil genérico de estudante.

Sou **CLT na Guarda Civil Municipal** há mais de 7 anos, **estudante de Engenharia de Software** (indo pro 5º semestre) e, fora do expediente, desenvolvo produtos pela **Sir Tech Solutions** — do desenho ao deploy, documentação e manutenção. Já tenho sistema **offline de guincho** entregue, gestão pra Pet Shop e Barbearia em produção, e um projeto de **segurança pública** (painel web + Android com Botão do Pânico, registro no INPI) voltado à realidade da GCM.

Minha dor financeira hoje não é “não ter salário”: é **não misturar o salário fixo da GCM com o que eu coloco nos meus sistemas** — ferramentas, horas de desenvolvimento, melhorias nos produtos. Sem separar direito, não sei se a reserva pessoal tá ok ou se tô puxando demais do bolso da família por causa do negócio paralelo.

---

## Passo 1 — Papel do Educador Financeiro

Crie a ideia de um Educador Financeiro Inteligente voltado para **profissionais com renda fixa CLT que também empreendem em tech de forma autônoma** — dev full cycle com produtos próprios ou projetos reais em produção.

O principal problema dessa pessoa é **confundir finanças pessoais com investimento no negócio** (tempo, melhorias, materiais, deslocamento) e não ter um lugar simples pra enxergar as duas coisas separadas.

A solução deve ajudar o usuário a **separar caixa pessoal e caixa do negócio, planejar um mês mais apertado e manter reserva pessoal sem abandonar os projetos que já estão rodando**.

O sistema deve se comunicar de forma **objetiva e responsável** — linguagem de quem já lida com pressão e decisão rápida (no meu caso, vivência de GCM), sem moralismo e sem prometer investimento milagroso.

---

## Passo 2 — Recursos e experiências inteligentes

O Educador Financeiro Inteligente deve possuir os seguintes recursos:

1. **Duas caixas: Pessoal (CLT) e Sir Tech / projetos** — salário, moradia, reserva de um lado; gastos e reinvestimento ligados aos produtos do outro.
2. **Simulador “mês sem entrada nova de projeto”** — e se só entrar o CLT? O que reduzir ou adiar sem prejudicar o que o cliente já usa (pet shop, barbearia, etc.).
3. **Visão por produto** — offline entregue (guincho) vs sistemas que você segue evoluindo (web/mobile), pra lembrar que cada um pesa diferente no bolso e no tempo.
4. **Meta de reserva pessoal** — acompanhar um valor mensal que você define (ex.: guardar um percentual fixo do salário CLT) com barra simples.

A IA deve adaptar as recomendações com base em **salário CLT, quanto foi reinvestido nos produtos, quantos projetos ativos, meta de reserva pessoal e prioridade do momento (estudo, entrega, manutenção)**.

Evite respostas **genéricas, jargão de investimento, indicação de produto financeiro ou promessa de rentabilidade**. Não substituir contador ou advogado.

As sugestões devem ser apresentadas no formato **lista curta, valores em R$ quando couber, exemplo ligado a quem mantém software em produção e um único próximo passo**.

---

## Passo 3 — Prompt final

```text
Atue como um especialista em educação financeira digital.
Crie a proposta de um Educador Financeiro Inteligente para profissionais CLT que também desenvolvem e mantêm sistemas de forma autônoma (produtos próprios, clientes reais, web, mobile e offline).

O sistema deve ajudar a separar finanças pessoais (salário fixo) do caixa do negócio tech, simular um mês sem nova receita de projetos e proteger a reserva pessoal sem travar o que já está em produção.

As principais funcionalidades devem incluir:
- Painel com duas caixas: Pessoal (CLT) e Negócio (projetos/produtos)
- Simulador "mês só com salário CLT" com prioridades do que adiar ou manter
- Visão por produto: sistema offline entregue vs sistemas em evolução contínua
- Acompanhamento de meta de reserva pessoal com barra de progresso

A comunicação deve ser objetiva, respeitosa e prática — como orientação para quem já entrega software de verdade.

As respostas devem vir em listas curtas, exemplos em R$, linguagem acessível e um único próximo passo por vez.

Evite jargão bancário, texto vago, promessa de rentabilidade e recomendações que pareçam venda de produto financeiro.

Personalize com base em: valor do salário CLT, reinvestimento mensal em projetos, quantidade de produtos em produção e meta de reserva pessoal.

No final, sugira como virar projeto frontend interativo com React, Vite e Tailwind CSS: telas, componentes reutilizáveis e gamificação leve (badge de "mês equilibrado", barra de reserva, etc).
```

---

## Minhas ideias de frontend (React + Tailwind)

Rabiscado pensando no que **eu** usaria na Sir Tech — React, Vite e Tailwind, stack que já uso no dia a dia.

### Ideia 1 — Home “CLT vs Sir Tech”

Dois blocos: entrada GCM + gastos pessoais; reinvestimento e gastos ligados aos projetos. Barra de **reserva pessoal** separada do “caixa Sir Tech”.

Componentes: `PersonalLedgerCard`, `BusinessLedgerCard`, `ReserveProgressBar`.

Badge **“Mês equilibrado”** quando a reserva pessoal bate a meta que eu defini no começo do mês.

### Ideia 2 — Mapa de projetos

Cards por produto: **Guincho (offline entregue)**, **Pet/Barbearia (em produção)**, **Segurança pública / GCM (em desenvolvimento)**. Status simples: entregue, em uso, em evolução.

`ProjectTile`, `StatusBadge`, `OfflineTag` vs `OnlineTag`.

### Ideia 3 — Simulador “só CLT este mês”

Botão que zera entradas de projeto no mês e lista o que é essencial manter (suporte ao cliente) vs o que pode esperar (feature nova, refatoração grande).

`ScenarioToggle`, `PriorityList`, checkbox do que eu aceito adiar.

Mobile first com Tailwind — consulta rápida entre turno e código.
