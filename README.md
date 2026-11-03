# Site Jessica Castanheira Caeiro

Site estático (GitHub Pages). As avaliações do Google são atualizadas sozinhas 2x por dia.

## Subir o site (uma vez)
1. Crie um repositório no GitHub (ex.: `site-jessica`) e envie todos estes arquivos para a raiz.
2. Settings → Pages → Source: "Deploy from a branch" → branch `main`, pasta `/ (root)` → Save.

## Ativar as avaliações automáticas
1. Place ID: abra https://developers.google.com/maps/documentation/places/web-service/place-id, procure o perfil e copie o código que começa com `ChIJ`.
2. Em `scripts/atualizar-avaliacoes.mjs`, troque `COLE_AQUI_O_PLACE_ID` pelo código.
3. Settings → Secrets and variables → Actions → New repository secret. Name: `SERPAPI_KEY`. Secret: a chave do SerpApi.
4. Aba Actions → "Atualizar avaliações do Google" → Run workflow.
5. Em cerca de 1 minuto aparece `avaliacoes.json` no repositório e o site mostra as avaliações.
6. Se der erro de permissão: Settings → Actions → General → Workflow permissions → "Read and write permissions" → Save e rode de novo.

Depois disso, a rotina roda sozinha às 6h e às 18h (horário de Brasília).

Obs.: enquanto o `avaliacoes.json` estiver vazio, o site mostra as duas avaliações escritas no HTML.
