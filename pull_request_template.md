<!--
  HOMOLOGAÇÃO: feature/* → homolog
  Produção: ?template=production.md · Hotfix: ?template=hotfix.md
  Pergunta deste PR: "está pronto para ser testado em homologação?"
-->

## O que muda

<!-- 2 ou 3 frases. O porquê importa mais que o quê. -->

## Card e spec

- Card: #
- Spec:
- RNs cobertas:
- ADRs aplicadas:

## Como testar em homologação

<!-- Roteiro que outra pessoa consegue seguir sem te perguntar nada. Pense no casal e no cerimonialista. -->

- **Perfil e casamento de teste:**
- **Dados de exemplo necessários:**

1.
2.

**Resultado esperado:**

## Prints

<!-- Obrigatório se mexe em tela: celular (390 px), tablet (768 px) e computador (1440 px). Sem dado real de casal ou convidado. -->

## Mudanças de dados e configuração

- [ ] Não há migration, seed ou variável de ambiente nova
- [ ] Migration revisada e compatível com a versão anterior (o deploy não quebra quem ainda roda o código antigo)
- [ ] Seed atualizado para entidade nova (idempotente, travado contra produção)
- [ ] Variável de ambiente nova criada em homologação e listada no `.env.example`
- [ ] Atrás de feature flag: `nome-da-flag` (estado em homologação: ligada / desligada)

## Checklist (DoD)

**Isolamento e segurança**
- [ ] Tabela nova do casamento tem `weddingId`, policy de RLS e FK composta
- [ ] Há teste provando que um usuário de outro casamento não lê nem escreve
- [ ] Autorização por papel conferida (casal, cerimonialista, convidado)
- [ ] Nenhum dado pessoal de convidado vai para log
- [ ] Ação sensível registrada no log da aplicação

**Produto**
- [ ] Pensado para o casal e para o cerimonialista
- [ ] Textos seguem Voz & Microcopy e passam pelo i18n
- [ ] Ação destrutiva ou irreversível tem modal explicando a consequência
- [ ] Responsivo (390, 768 e 1440 px), sem rolagem horizontal, alvo de toque de 44 px

**Técnico**
- [ ] Testes unitários do caminho feliz e dos caminhos tristes da spec
- [ ] E2E, quando o fluxo exige
- [ ] SQL manual de RLS e índices parciais revisado na migration
- [ ] Contrato da API (OpenAPI) atualizado para rota criada, alterada ou removida
- [ ] Modelo de Dados, Contratos e Glossário atualizados, se mudaram
