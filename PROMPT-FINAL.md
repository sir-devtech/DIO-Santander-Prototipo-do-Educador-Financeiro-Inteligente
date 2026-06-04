# Educador Financeiro Inteligente — Desafio Criativo (DIO)

Trilha Santander 2026 - React Frontend  
Moisés Santos | GitHub: sir-devtech | Sir Tech Solutions

Montei esse desafio a partir do **meu** contexto, não de um perfil genérico de estudante.

Sou **CLT na Guarda Civil Municipal** há mais de 7 anos, **estudante de Engenharia de Software** (indo pro 5º semestre) e, fora do expediente, desenvolvo produtos pela **Sir Tech Solutions** — do desenho ao deploy, documentação e manutenção. Já tenho sistema **offline de guincho** entregue, gestão pra Pet Shop e Barbearia em produção, e um projeto de **segurança pública** (painel web + Android com Botão do Pânico, registro no INPI) voltado à realidade da GCM.

Minha dor financeira hoje não é “não ter salário”: é **não misturar o salário fixo da GCM com o caixa dos meus sistemas**. AWS, Digital Ocean, domínio, ferramenta e hora de dev viram custo — e sem separar direito eu não enxergo se o projeto se paga, se a reserva pessoal tá ok ou se tô subsidiando produto com o salário público (no sentido organizacional, não jurídico).

---

## Passo 1 — Papel do Educador Financeiro

Crie a ideia de um Educador Financeiro Inteligente voltado para **profissionais com renda fixa CLT que também empreendem em tech de forma autônoma** — dev full cycle com produtos próprios ou projetos reais em produção.

O principal problema dessa pessoa é **confundir finanças pessoais com investimento em produto** (nuvem, licença, hardware, tempo de desenvolvimento) e não ter um “painel único” que respeite a estabilidade do emprego e o risco do negócio paralelo.

A solução deve ajudar o usuário a **separar caixa pessoal e caixa do negócio, enxergar custo de infra e ferramentas, simular um mês apertado e manter reserva pessoal sem abandonar os projetos**.

O sistema deve se comunicar de forma **objetiva e responsável** — linguagem de quem já lida com pressão e decisão rápida (no meu caso, vivência de GCM), sem moralismo e sem prometer investimento milagroso.

---

## Passo 2 — Recursos e experiências inteligentes

O Educador Financeiro Inteligente deve possuir os seguintes recursos:

1. **Duas caixas: Pessoal (CLT) e Sir Tech / projetos** — salário, moradia, reserva de um lado; AWS, DO, domínio, ferramentas e custo de entrega do outro.
2. **Painel de custo de infra** — soma mensal de cloud e CI/CD; avisa quando passar de um teto (eu começaria monitorando a partir de **R$ 200/mês** em serviços, ajustando conforme o projeto).
3. **Simulador “mês sem faturamento novo”** — e se só entrar o CLT e nenhum cliente novo? O que pausar na nuvem sem matar o que já está em produção (ex.: pet shop, barbearia).
4. **Checklist por tipo de produto** — offline (guincho: custo baixo recorrente) vs online (sistemas web/mobile: custo contínuo de hospedagem e monitoramento).

A IA deve adaptar as recomendações com base em **salário CLT, quanto foi reinvestido em produtos, quantos projetos ativos em produção, meta de reserva pessoal e se há custo fixo de nuvem ou entrega pontual**.

Evite respostas **genéricas, jargão de investimento, indicação de produto financeiro ou promessa de rentabilidade**. Não substituir contador ou advogado.

As sugestões devem ser apresentadas no formato **lista curta, valores em R$, exemplo ligado a dev que mantém sistema em produção e um único próximo passo**.

---

## Passo 3 — Prompt final

```text
Atue como um especialista em educação financeira digital.
Crie a proposta de um Educador Financeiro Inteligente para profissionais CLT que também desenvolvem e mantêm sistemas de forma autônoma (produtos próprios, clientes reais, web, mobile e offline).

O sistema deve ajudar a separar finanças pessoais (salário fixo) do caixa do negócio tech, visualizar custos de infraestrutura (cloud, domínio, ferramentas, CI/CD), simular um mês sem nova receita de projetos e proteger a reserva pessoal sem travar o que já está em produção.

As principais funcionalidades devem incluir:
- Painel com duas caixas: Pessoal (CLT) e Negócio (projetos/produtos)
- Monitor de custo mensal de infra e alerta de teto configurável
- Simulador "mês só com salário CLT" com cortes priorizados (o que pausar na nuvem vs o que é essencial)
- Visão por tipo de produto: sistema offline entregue vs SaaS/web em produção

A comunicação deve ser objetiva, respeitosa e prática — como orientação para quem já entrega software de verdade.

As respostas devem vir em listas curtas, exemplos em R$, linguagem acessível e um único próximo passo por vez.

Evite jargão bancário, texto vago, promessa de rentabilidade e recomendações que pareçam venda de produto financeiro.

Personalize com base em: valor do salário CLT, reinvestimento mensal em projetos, quantidade de produtos em produção, meta de reserva pessoal e perfil de custo (mais cloud contínuo ou mais entrega/offline).

No final, sugira como virar projeto frontend interativo com React, Vite e Tailwind CSS: telas, componentes reutilizáveis e gamificação leve (badge de "mês equilibrado", barra de reserva, etc).
```

---

## Minhas ideias de frontend (React + Tailwind)

Rabiscado pensando no que **eu** usaria na Sir Tech — stack que já trabalho (React, Vite, Tailwind), não template de app genérico.

### Ideia 1 — Home “CLT vs Sir Tech”

Dois blocos: entrada GCM + gastos pessoais; saídas de infra (AWS/DO), ferramentas e horas estimadas nos projetos. Barra de **reserva pessoal** separada do “caixa reinvestimento”.

Componentes: `PersonalLedgerCard`, `BusinessLedgerCard`, `ReserveProgressBar`.

Badge **“Mês equilibrado”** quando reserva pessoal bate meta e infra não estourou o teto.

### Ideia 2 — Mapa de projetos reais

Cards por produto: **Guincho (offline)**, **Pet/Barbearia (web em produção)**, **GCM / segurança pública (web + Android)**. Cada um mostra custo recorrente estimado e botão “simular pausa de ambiente”.

`ProjectTile`, `CostTag`, `OfflineBadge` vs `CloudBadge`.

Ajuda a lembrar que offline não é “zero custo”, mas a lógica é outra — igual eu aprendi entregando o guincho.

### Ideia 3 — Alerta infra + DevOps

Lista de itens: Digital Ocean, AWS, domínio, GitHub Actions. Usuário define teto; passou, banner com **uma** ação (ex.: revisar ambiente de homologação ocioso).

`InfraLineItem`, `ThresholdAlert` — conectado ao jeito que já cuido de deploy e ambiente.

Mobile first com Tailwind, porque parte da operação eu imagino consultando rápido, no intervalo entre turno e código.
