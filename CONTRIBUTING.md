# Como contribuir com o Kore

Obrigado por contribuir! Este guia vale para todos os repositórios da organização **kore-io**, a não ser que o repositório tenha o seu próprio `CONTRIBUTING.md`.

O passo a passo de cada repositório (instalação, variáveis de ambiente, comandos) fica no `README.md` dele. As decisões de produto e de arquitetura ficam no cofre de documentação (`docs-kore-hub`), que é a fonte única da verdade.

## Antes de começar

1. Todo trabalho nasce de um **card** no Kanban Kore. Feature nasce de uma **spec aprovada** (passou pelo DoR).
2. Termo novo do domínio entra primeiro no Glossário, depois no código.
3. Decisão cara de reverter, que afeta várias features ou que envolve segurança, LGPD ou dinheiro pede uma **ADR** antes do código.

## Branches

Usamos um Git Flow simplificado:

| Branch | Para quê | Sai de | Entra em |
|---|---|---|---|
| `production` | O que está em produção | — | — |
| `homolog` | Integração e homologação | — | `production` |
| `feature/*` | Trabalho novo | `homolog` | `homolog` |
| `hotfix/*` | Correção urgente em produção | `production` | `production` **e** `homolog` |

Nome da branch: `tipo/<card_id>-descricao-curta`, por exemplo `feature/12-lista-de-convidados` ou `hotfix/58-webhook-duplicado`.

`production` e `homolog` são protegidas: não aceitam push direto, exigem CI verde, e `production` só recebe PR de `homolog` ou de `hotfix/*`.

Repositórios que não têm deploy (`docs-kore-hub`, `tool-kore-bruno`) usam só a `main`.

## Commits

Seguimos o [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/). O commitlint confere a mensagem no pre-commit e no CI.

```
<tipo>(<escopo>): <resumo no imperativo, minúsculo, sem ponto final>
```

| Tipo | Quando usar |
|---|---|
| `feat` | Funcionalidade nova |
| `fix` | Correção de bug |
| `refactor` | Mudança de código sem mudar comportamento |
| `perf` | Melhoria de desempenho |
| `test` | Testes |
| `docs` | Documentação |
| `build` | Dependências, build, Docker |
| `ci` | Pipelines do GitHub Actions |
| `chore` | Manutenção que não entra em nenhum dos outros |

O escopo é o módulo ou contexto do domínio: `feat(rsvp): ...`, `fix(gifts): ...`.

Mudança que quebra contrato (API, pacote `@kore/design`) leva `!` depois do tipo e um rodapé `BREAKING CHANGE:` explicando o impacto.

## Pull requests

- Um PR = um card. PR pequeno é revisado mais rápido e com mais cuidado.
- Preencha o modelo de PR: ele traz o checklist da Definition of Done.
- Título no mesmo formato dos commits: `feat(rsvp): confirma presença por pessoa do grupo`.
- Link para o card e para a spec no corpo do PR.
- O merge só acontece com CI verde e pelo menos uma aprovação.
- Para abrir um PR de release ou de hotfix, acrescente `?template=release.md` ou `?template=hotfix.md` ao endereço de criação do PR.

## Padrões de código

- **Código em inglês**, com os nomes do Glossário. **Interface em pt-BR**, sempre via i18n.
- ESLint + Prettier rodam no pre-commit e no CI. Não desligue regra sem explicar o porquê no próprio código.
- Parâmetros de função sempre nomeados (objeto desestruturado).
- Comentário explica o **porquê**, não o quê.
- Dinheiro em centavos inteiros; datas em UTC no banco.
- Teste citando a regra de negócio: `it("RN03 - recusa a 11ª tag do casamento")`.

## Segurança e privacidade

- Nunca faça commit de `.env`, chave, token ou dado real de cliente. Use o `.env.example`.
- Dado pessoal de convidado nunca vai para log.
- Encontrou uma vulnerabilidade? **Não abra issue.** Siga o [SECURITY.md](SECURITY.md).

## Revisão de código

Quem revisa olha, nesta ordem:

1. A mudança faz o que a spec pede, citando as RNs?
2. Isolamento entre casamentos e autorização por papel continuam garantidos?
3. Há testes para o caminho feliz e para os caminhos tristes da spec?
4. O código segue as convenções e as ADRs vigentes?

Comentário de revisão é sobre o código, nunca sobre a pessoa. Use os prefixos `bloqueante:`, `sugestão:` e `dúvida:` para deixar claro o peso de cada comentário.
