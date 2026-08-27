# Dashboard — Diligências

Backlog e cumprimento das diligências do escritório Borges Macedo Advocacia, alimentado
em tempo real pela planilha **"Diligências"** do Google Sheets.

**Acesso exclusivo das lideranças.** Só os perfis **Administração** e **Lideranças** têm
cofre neste painel.

## O que é exibido

| Seção | Conteúdo |
|---|---|
| Resumo Executivo | Diligências lançadas, em aberto, taxa de cumprimento, idade média do backlog, abertas há mais de 7 dias, cobertura de contato, valores a receber e diligências sem responsável |
| Backlog e Envelhecimento | Situação (pendente/solicitada/cumprida), distribuição do backlog por faixa de idade e ciclo médio de cumprimento |
| Onde as Diligências Travam | Concentração por tribunal e comarca, e ranking de varas por represamento com o canal de contato mapeado |
| Tipo de Diligência | Volume e cumprimento por tipo de pedido, com idade média de cada fila |
| Execução e Canal | Cobertura de e-mail, balcão virtual e atendimento presencial; carga por responsável |
| Valores a Receber | Fila específica de cobrança e liberação de valores — a de impacto direto em caixa |
| Fila de Trabalho | Diligências filtráveis, das mais antigas para as mais recentes |
| Pontos de Atenção | Leitura executiva automática dos números |

## Leitura executiva embutida

- **Taxa de cumprimento muito baixa** — distingue o represamento real do simples não
  registro da baixa na planilha; nos dois casos a liderança fica sem visibilidade.
- **Envelhecimento do backlog** — cada dia parado é processo parado, e quando envolve
  alvará é caixa que não entra.
- **Execução concentrada em uma pessoa** — dispara quando um único responsável passa de
  60% da carga: férias ou desligamento param a frente inteira.
- **Lançadas sem tentativa registrada** — lançar na planilha não é diligenciar; sem
  registro não há como cobrar retorno nem comprovar diligência ao cliente.
- **Concentração por tribunal e vara** — volume concentrado justifica tratativa
  institucional em vez de insistência caso a caso.
- **Valores a receber pendentes** — a fila com efeito mais direto no caixa.

## Como funciona

- Lê as abas **TODAS AS DILIGÊNCIAS** e **VALORES A RECEBER** pela **Sheets API v4**.
- Leitura por nome de cabeçalho com fallback pela letra da coluna.
- Linhas em que o cabeçalho se repete no meio da aba são descartadas (a aba de valores
  tem o cabeçalho repetido algumas vezes).
- Idade e ciclo são calculados sobre a data do dia, então o painel envelhece sozinho.
- Atualização automática a cada 5 minutos. Arquivo único `index.html`, sem build.
