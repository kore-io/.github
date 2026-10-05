<!-- Modelo padrão: feature/* → homolog. Release: ?template=release.md · Hotfix: ?template=hotfix.md -->

## O que muda

<!-- 2 ou 3 frases. O porquê importa mais que o quê. -->

## Card e spec

- Card: #
- Spec:
- RNs cobertas:
- ADRs aplicadas:

## Como testar

1.

## Prints

<!-- Obrigatório se mexe em tela: celular (390 px), tablet (768 px) e computador (1440 px). -->

## Checklist (DoD)

**Isolamento e segurança**
- [ ] Tabela nova do casamento tem `weddingId`, policy de RLS e FK composta
- [ ] Há teste provando que um usuário de outro casamento não lê nem escreve
- [ ] Autorização por papel conferida
- [ ] Nenhum dado pessoal de convidado vai para log
- [ ] Ação sensível registrada no log da aplicação

**Produto**
- [ ] Textos seguem Voz & Microcopy e passam pelo i18n
- [ ] Ação destrutiva ou irreversível tem modal explicando a consequência
- [ ] Responsivo (390, 768 e 1440 px), sem rolagem horizontal, alvo de toque de 44 px

**Técnico**
- [ ] Testes unitários do caminho feliz e dos caminhos tristes da spec
- [ ] E2E, quando o fluxo exige
- [ ] Migration revisada (SQL manual de RLS e índices parciais)
- [ ] OpenAPI atualizado para rota criada, alterada ou removida
- [ ] Seed atualizado para entidade nova
- [ ] Modelo de Dados, Contratos e Glossário atualizados, se mudaram
