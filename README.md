# Escala Extra · PM

Aplicativo (PWA) para controlar as escalas extras da Polícia Militar: DEJEM, Delegada e outros tipos, com os valores a receber e o que já foi recebido.

Publicado em: https://escala-pm.lielton-medeiros.workers.dev/

## O que faz

- Calendário mensal com feriados nacionais e de São Paulo (fins de semana e feriados em vermelho).
- **Marcação** de escala (DEJEM em azul claro, Delegada em verde claro): a escala fica prevista, sem entrar nos valores, até ser confirmada.
- **Confirmação**: no dia, toque em *Confirmar*. O valor padrão do tipo é preenchido e pode ser ajustado.
- Modo de marcação rápida: escolha *Marcar DEJEM* ou *Marcar Delegada* acima do calendário e toque nos dias.
- Resumo do mês: a receber, pendente, recebido, quantidade de marcadas e previsão.
- Tipos de escala configuráveis (nome, cor e valor padrão), tema claro/escuro.
- Backup: exportar e importar os dados em arquivo `.json`.
- Funciona offline e pode ser instalado na tela inicial.

Os dados ficam só no aparelho (localStorage). Nada é enviado para servidor.

## Arquivos

| Arquivo | Função |
|---|---|
| `index.html` | O app inteiro (React 18 + Babel no navegador, sem build) |
| `manifest.json` | Dados do app para instalação |
| `sw.js` | Service worker (cache offline) |
| `icons/` | Ícones |

## Publicar uma nova versão

1. Altere a constante `VERSAO` no `sw.js` (ex.: `escala-pm-v3`), para os celulares baixarem a atualização.
2. Cloudflare → Workers & Pages → `escala-pm` → **New deployment** → envie `index.html`, `manifest.json`, `sw.js` e a pasta `icons` (com o `index.html` na raiz).
