# .github

Arquivos padrão da organização **kore-io** no GitHub.

O GitHub usa os arquivos deste repositório em **todo** repositório da organização que não tiver o seu próprio arquivo do mesmo tipo, seja ele público ou privado. Se um repositório criar o próprio `CONTRIBUTING.md`, por exemplo, ele substitui o daqui só naquele repositório.

> ⚠️ Este repositório é **público**, porque o GitHub exige isso. Nada de segredo, arquitetura interna, endereço de ambiente de homologação ou dado de cliente aqui. Esse conteúdo fica no `docs-kore-hub`.

## O que tem aqui

| Arquivo | Para que serve |
|---|---|
| `profile/README.md` | Página pública da organização em github.com/kore-io |
| `CONTRIBUTING.md` | Como contribuir: branches, commits, PRs e revisão |
| `CODE_OF_CONDUCT.md` | Código de conduta |
| `SECURITY.md` | Como reportar uma vulnerabilidade |
| `SUPPORT.md` | Onde pedir ajuda (cliente × time) |
| `ISSUE_TEMPLATE/` | Formulários de issue: bug, melhoria e tarefa técnica |
| `pull_request_template.md` | Modelo padrão de PR (`feature/*` → `homolog`) |
| `PULL_REQUEST_TEMPLATE/` | Modelos de PR para release (`homolog` → `production`) e hotfix |
| `workflow-templates/` | Modelo de CI (GitHub Actions) que aparece em **Actions → New workflow** em cada repositório |

## O que **não** dá para definir aqui

Estes arquivos precisam existir em cada repositório, porque o GitHub não aceita um padrão da organização para eles:

- `LICENSE`
- `CODEOWNERS`
- `.github/dependabot.yml`
- `.github/workflows/*.yml` (o modelo daqui só facilita a criação)

A proteção das branches `production` e `homolog` é configurada pelo Terraform no `tool-kore-infra`.

## Página só para membros

Para mostrar uma página interna a quem é membro da organização (links do cofre, Penpot, ambientes), crie um repositório **privado** chamado `.github-private` com um `profile/README.md`.
