# Como contribuir

Os repositórios da organização **kore-io** são privados: só membros do time abrem issues e pull requests. As regras abaixo valem para todos eles, a não ser que o repositório tenha o seu próprio `CONTRIBUTING.md`.

O **guia completo do time** (repositórios, branches, convenções de código, Definition of Done e revisão) fica no cofre de documentação, `docs-kore-hub`, nas notas *Convenções* e *Deploy & Infra*. Este arquivo é público e traz só o essencial.

## Antes de começar

- Todo trabalho nasce de um **card** no Kanban. Feature nasce de uma **spec aprovada**.
- O casal e o cerimonialista têm a mesma importância: toda mudança é pensada para os dois.
- O passo a passo de cada repositório (instalação, variáveis de ambiente, comandos) fica no `README.md` dele.

## Commits

Seguimos o [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/). O commitlint confere a mensagem no pre-commit e no CI.

```
<tipo>(<escopo>): <resumo no imperativo, minúsculo, sem ponto final>
```

Tipos: `feat`, `fix`, `refactor`, `perf`, `test`, `docs`, `build`, `ci` e `chore`. Mudança que quebra contrato leva `!` depois do tipo e um rodapé `BREAKING CHANGE:`.

Use o **e-mail corporativo** ou o e-mail `noreply` do GitHub no `git config user.email`, nunca um e-mail pessoal.

## Pull requests

- Um PR = um card. Preencha o modelo de PR: ele traz o checklist da Definition of Done.
- Título no mesmo formato dos commits.
- O merge só acontece com CI verde e pelo menos uma aprovação.
- O modelo padrão é o de **homologação**. Para levar `homolog` a produção ou abrir um hotfix, acrescente `?template=production.md` ou `?template=hotfix.md` ao endereço de criação do PR.

## Segurança e privacidade

Os dados dos convidados pertencem ao casal. Segurança e privacidade vêm desde o início, não depois.

- Nunca faça commit de `.env`, chave, token ou dado real de cliente.
- Dado pessoal de convidado nunca vai para log.
- Encontrou uma vulnerabilidade? **Não abra issue.** Siga o [SECURITY.md](SECURITY.md).

## Revisão de código

Comentário de revisão é sobre o código, nunca sobre a pessoa. Use os prefixos `bloqueante:`, `sugestão:` e `dúvida:` para deixar claro o peso de cada comentário.
