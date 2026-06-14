# quartz7k — página pessoal

site de apresentação pessoal com estética dark/monospace, integração com Discord via Lanyard e players do Spotify embutidos.

---

## estrutura

```
📁 repositório/
├── index.html        ← estrutura e conteúdo
├── 📁 styles/
│   └── style.css     ← visual e layout
└── 📁 imgs/
    └── HeikeVIKaiserPony.jpg
```

---

## funcionalidades

- **presença do Discord em tempo real** via [Lanyard](https://github.com/phineas/lanyard) — mostra jogo aberto e música tocando
- **players do Spotify embutidos** — 6 faixas favoritas com player nativo
- **seções em accordion** — todas fechadas por padrão, uma abre por vez
- **horário em tempo real** no fuso de Brasília
- **responsivo** para mobile

---

## seções

| seção | descrição |
|---|---|
| sobre mim | bio |
| interesses & hobbies | música, código, jogos, escrita |
| jogos favoritos | 6 jogos com gênero e nota pessoal |
| frases favoritas | citações que eu gosto |
| top músicas | 6 faixas com player do Spotify |
| links | redes sociais e projetos |

---

## como editar

### trocar a foto
substitua o arquivo em `imgs/` e atualize o `src` no `index.html`:
```html
<img src="imgs/sua-foto.jpg" alt="avatar" style="width:100%;height:100%;object-fit:cover;" />
```

### adicionar/trocar músicas
pegue o ID da música no Spotify: abra a faixa → `...` → Compartilhar → Copiar link  
o link tem o formato `https://open.spotify.com/track/XXXXXXXXXXXXXXXXXXXXXXXX`  
use só o ID (parte depois de `/track/`) no embed:
```html
<iframe src="https://open.spotify.com/embed/track/SEU_ID_AQUI?utm_source=generator&theme=0" ...></iframe>
```

### configurar o Discord (Lanyard)
1. entre no servidor do Lanyard: [discord.gg/lanyard](https://discord.gg/lanyard)
2. o Discord ID já está configurado no `index.html`:
```js
const DISCORD_ID = '1213505861952212993';
```
3. a presença atualiza automaticamente a cada 15 segundos

### editar notas dos jogos
no `index.html`, procure cada `.game-note` e substitua o texto:
```html
<span class="game-note">seu comentário sobre o jogo</span>
```

### trocar frases
no `index.html`, procure os blocos `.quote-block`:
```html
<div class="quote-block">
  <p class="quote-text">sua frase aqui</p>
  <span class="quote-author">Autor</span>
</div>
```

---

## tecnologias

- HTML / CSS puro — sem frameworks
- [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) via Google Fonts
- [Lanyard API](https://api.lanyard.rest) para presença do Discord
- Spotify Embed API para os players

---

## deploy

hospedado via **GitHub Pages** em  
[`https://lucy7x.github.io/V1/`]
