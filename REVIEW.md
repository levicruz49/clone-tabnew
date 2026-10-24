# REVIEW.md

O que importa revisar no clone-tabnew. Lido pelo Codex no PR e pelo juiz do
pre-push. Só acrescenta critério aos centrais
(Agents-config/templates/codex-review/pedido.md); não afrouxa nenhum.

Projeto de estudo (Next.js, pages router). Hoje tem um arquivo de código,
`pages/index.js`, sem autenticação, banco, variável de ambiente nem rota de API.

## Áreas críticas

- Primeira rota em `pages/api/`, primeira conexão a banco ou primeiro
  `process.env`: daí em diante este arquivo precisa ganhar a área nova.
  Conferir: credencial vem de variável de ambiente, `.env` no `.gitignore` e
  `.env.example` sem valor.

## Invariantes de negócio

- Nenhuma ainda.

## O que bloqueia neste projeto

- Credencial ou string de conexão escrita no código ou em arquivo versionado.
- Script `test` (jest) apontado como verde sem nenhum arquivo de teste: hoje
  não existe `*.test.js` nem `*.spec.js`.

## O que ignorar

Ignorar vale só para estilo e lógica: segredo, PII, credencial e mudança em gate continuam bloqueando em qualquer caminho, inclusive nos listados abaixo.

- `node_modules/`, `.next/`, `package-lock.json`.
