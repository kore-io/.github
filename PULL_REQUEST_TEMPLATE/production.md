<!--
  PRODUÇÃO: homolog → production
  Pergunta deste PR: "é seguro colocar isto na frente dos casais, cerimonialistas e convidados agora, e sabemos voltar atrás?"
  Não aprove sem plano de volta e sem alguém acompanhando o deploy.
-->

## Release

- **Data e horário do deploy:**
- **Responsável pelo deploy:** @
- **Quem acompanha depois do deploy:** @

## O que entra

| Card | Título | Tipo | Risco |
|---|---|---|---|
| # | | feat / fix / chore | baixo / médio / alto |

## Nível de risco da release

- [ ] **Baixo**: texto, visual ou mudança isolada, sem migration e sem tocar em fluxo crítico
- [ ] **Médio**: funcionalidade nova ou alterada, migration compatível com a versão anterior
- [ ] **Alto**: confirmação de presença, site do casal, pagamentos, autorização, RLS, dados pessoais, migration destrutiva ou mudança que quebra contrato

<!-- Risco alto: aprovação do Product Owner e deploy atrás de feature flag ou com janela combinada. -->

## Go / no-go

- [ ] Todos os cards da lista estão `verified` em homologação (DoD completo)
- [ ] E2E obrigatórios verdes em homologação
- [ ] Nenhum bug crítico ou alto aberto para o que entra
- [ ] Migrations conferidas: compatíveis com a versão anterior ou com janela combinada
- [ ] Variáveis de ambiente e segredos novos já criados em produção
- [ ] Nenhuma mudança que quebra contrato sem nova versão da API ou do pacote de design
- [ ] Deploy fora dos horários de pico (fins de semana e vésperas de casamento), se mexe em site do casal ou confirmação de presença
- [ ] Aprovação do Product Owner (obrigatória para risco alto): @

## Plano de implantação

- [ ] De uma vez
- [ ] Atrás de feature flag, ligada aos poucos: `nome-da-flag` (casamentos piloto → todos)
- [ ] Em janela combinada

## Plano de volta

<!-- Decidido ANTES do deploy, não durante o problema. -->

**Voltamos se**, nos primeiros 30 minutos:
- a taxa de erro subir acima do normal;
- o site do casal, a confirmação de presença ou o painel falharem para qualquer casamento;
- aparecer qualquer sinal de dado de um casamento visível para outro.

**Como voltar:**
1. <!-- desligar a flag / reverter o deploy para a versão anterior -->
2. <!-- migration de volta, se houver, ou por que não é necessária -->

## Comunicação

- [ ] Não precisa avisar ninguém
- [ ] Casais e cerimonialistas avisados antes (mudança visível ou janela de indisponibilidade)
- [ ] Notas de versão publicadas

## Depois do deploy

- [ ] Deploy concluído e versão conferida em produção
- [ ] Health check verde
- [ ] Fluxos críticos conferidos em produção (login, site do casal, confirmação de presença, painel do casal e do cerimonialista)
- [ ] Painéis de observabilidade sem erro novo durante a janela de acompanhamento
- [ ] Cards movidos no Kanban
