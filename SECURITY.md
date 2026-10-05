# Política de segurança

A segurança dos dados dos casais e dos convidados é prioridade no Kore. Se você encontrou uma vulnerabilidade, agradecemos por nos avisar de forma responsável.

## Como reportar

**Não abra uma issue pública, não comente em PR e não divulgue a falha** antes de ela ser corrigida.

Reporte pelo **GitHub Private Vulnerability Reporting**: abra a aba **Security** do repositório afetado e clique em **Report a vulnerability**. Se não souber qual repositório é o afetado, use qualquer um da organização.

Inclua, se possível:

- o que a falha permite fazer e qual o impacto;
- o passo a passo para reproduzir (endereço, requisição, payload);
- a versão, o navegador ou o aparelho usados;
- como você sugere corrigir, se tiver uma ideia.

## O que esperar de nós

| Etapa | Prazo |
|---|---|
| Confirmação de recebimento | até 2 dias úteis |
| Avaliação inicial e classificação de gravidade | até 5 dias úteis |
| Atualizações sobre a correção | pelo menos a cada 7 dias |

Quando a falha envolver dados pessoais, seguimos o nosso plano de resposta a incidentes e as obrigações da LGPD, incluindo a comunicação à ANPD e aos titulares afetados quando for o caso.

Com a sua autorização, damos o crédito pela descoberta quando a correção for publicada.

## Escopo

**Dentro do escopo:**

- `kore.com.br` e os sites dos casais em `kore.com.br/<slug>`
- `app.kore.com.br`
- `api.kore.com.br`
- o código dos repositórios da organização **kore-io**

**Fora do escopo:**

- ataques de negação de serviço (DoS/DDoS) e testes de carga;
- engenharia social, phishing ou ataque físico contra o time ou os clientes;
- falhas em serviços de terceiros que usamos (reporte direto ao fornecedor);
- relatórios automáticos de scanners sem prova de impacto;
- ausência de cabeçalhos ou boas práticas sem uma exploração concreta.

## Regras para pesquisa de boa-fé

- Use apenas contas suas ou de teste. Nunca acesse, altere ou apague dados de outras pessoas.
- Se encontrar dados pessoais por acidente, pare, não guarde cópia e nos avise.
- Não degrade o serviço para os usuários.

Quem seguir estas regras agindo de boa-fé não sofrerá nenhuma ação nossa por causa da pesquisa.

No momento, o Kore não tem programa de recompensa (bug bounty).
