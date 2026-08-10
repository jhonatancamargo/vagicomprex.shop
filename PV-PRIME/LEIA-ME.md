# Clone estático — Vagicomprex (landing page)

Cópia **visualmente idêntica** da página `https://vagicomprex.com.br/`, pronta pra hospedar em outro domínio e rodar anúncio.

## O que é / o que não é
- ✅ **Landing 100% idêntica**: hero, benefícios, depoimentos, vídeo, WhatsApp, banner da Cátia, cards de preço, garantia, FAQ, countdown regressivo — tudo estático em HTML (renderiza sem servidor).
- ✅ **Checkout na SUA Yampi (VestMom)**: criei o produto **"Vagicomprex — Saúde Íntima Feminina"** na sua Yampi como 1 produto com variação (Kit: 1/3/6 frascos). Cada botão de kit da landing leva direto pro checkout do kit certo:
  - 1 Frasco (R$ 87,90 · de R$ 137,90) → `seguro.vestmom.com.br/r/E378ZCUIUM`
  - 3 Frascos (R$ 147,90 · de R$ 263,70) → `seguro.vestmom.com.br/r/1CDNJWADP9`
  - 6 Frascos (R$ 267,80 · de R$ 527,40) → `seguro.vestmom.com.br/r/P74QGRQTXF`
  Pra trocar os links, edite `KIT_LINKS` no `<script>` no fim do `index.html`.

## Antes de subir — 2 ajustes (opcionais)

Abra `index.html` e procure (Ctrl+F):

1. **Pixel do Facebook** → já configurado com o pixel **627260033595972** (dispara PageView + InitiateCheckout ao clicar num kit). Só mexa se trocar de pixel.

2. **`KIT_LINKS`** (perto do fim do arquivo, no `<script>`) → os 3 links de checkout da Yampi por kit, já preenchidos. Só mexa se trocar de produto/loja.

## Preview local
Pode dar **duplo-clique no `index.html`** que ele abre estilizado no navegador (os caminhos são relativos). Só mantenha o `index.html` junto das pastas `assets/` e `videos/`.

## Como hospedar

Sobe a pasta inteira (index.html + assets/ + videos/), mantendo a estrutura de pastas.

**Opção A — Cloudflare Pages (grátis, recomendado):**
1. cloudflare.com → Workers & Pages → Create → Pages → Upload assets.
2. Arraste a pasta `vagicomprex-clone` inteira.
3. Deploy. Depois é só apontar seu domínio em "Custom domains".

**Opção B — Netlify drop:** app.netlify.com/drop → arrasta a pasta. Domínio próprio em Site settings → Domain.

**Opção C — qualquer hospedagem:** joga os arquivos na pasta pública (public_html / www), mantendo a estrutura de pastas.

## Estrutura
```
index.html            ← página (edite pixel/checkout aqui)
assets/               ← imagens, css
videos/depoimento.mp4 ← vídeo de depoimento
```

## Observações
- WhatsApp: **sem número por enquanto** (o botão não faz nada). Pra ativar, coloque seu número na variável `WHATSAPP` no `<script>` do fim do `index.html` (formato `https://wa.me/55SEUNUMERO`).
- Countdown regressivo é evergreen (reinicia sozinho), igual ao original.
- FAQ e vídeo são nativos do HTML, funcionam sem depender de nada externo.
