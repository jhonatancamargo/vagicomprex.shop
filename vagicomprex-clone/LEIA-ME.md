# Clone estático — Vagicomprex (landing page)

Cópia **visualmente idêntica** da página `https://vagicomprex.com.br/`, pronta pra hospedar em outro domínio e rodar anúncio.

## O que é / o que não é
- ✅ **Landing 100% idêntica**: hero, benefícios, depoimentos, vídeo, WhatsApp, banner da Cátia, cards de preço, garantia, FAQ, countdown regressivo — tudo estático em HTML (renderiza sem servidor).
- ⚠️ **Checkout NÃO é copiado**: o checkout do site original é um sistema no servidor deles (Supabase + gateway de pagamento). Não dá pra copiar em HTML. Por isso, **os botões "Comprar agora" redirecionam pro checkout que já funciona** em `vagicomprex.com.br/#preco`. A venda continua rolando normal; só a landing fica no domínio novo.

## Antes de subir — 2 ajustes (opcionais)

Abra `index.html` e procure (Ctrl+F):

1. **`COLOQUE_SEU_PIXEL_AQUI`** (aparece 2x) → troque pelos números do seu **novo pixel** do Facebook.
   Enquanto estiver com esse texto, nenhum pixel dispara (nada quebra).

2. **`CHECKOUT_URL`** (perto do fim do arquivo, no `<script>`) → se quiser mandar os botões pra outro checkout (Kirvano, Kiwify, Cartpanda, etc.), troque a URL aqui. Padrão: `https://vagicomprex.com.br/#preco`.

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
- WhatsApp: botão aponta pra `wa.me/5575988452583` (mesmo número do original). Troque no `<script>` se quiser.
- Countdown regressivo é evergreen (reinicia sozinho), igual ao original.
- FAQ e vídeo são nativos do HTML, funcionam sem depender de nada externo.
