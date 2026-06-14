# quartz7k — página pessoal

site de apresentação pessoal com estética dark/monospace, integração com Discord via Lanyard, players do Spotify embutidos e banners da Steam nos jogos favoritos.

---

## estrutura

```
📁 repositório/
├── index.html          ← estrutura e conteúdo
├── 📁 styles/
│   └── style.css       ← visual, temas claro/escuro e layout
└── 📁 imgs/
    └── HeikeVIKaiserPony.jpg
```

---

## funcionalidades

- **presença do Discord em tempo real** via [Lanyard](https://github.com/phineas/lanyard)
  - mostra jogo aberto com ícone do Discord CDN
  - mostra música tocando com capa do álbum
  - ponto verde pulsante quando há atividade
  - atualiza a cada 15 segundos
- **players do Spotify embutidos** — 6 faixas com player nativo tema escuro
- **banners da Steam** desfocados no fundo dos cards de jogos favoritos
- **modo claro / escuro** com botão fixo no canto e preferência salva no navegador
- **seções em accordion** — todas fechadas por padrão, uma abre por vez
- **horário em tempo real** no fuso de Brasília
- **responsivo** para mobile

---

## seções

| seção | descrição |
|---|---|
| sobre mim | bio |
| interesses & hobbies | música, código, jogos, escrita |
| jogos favoritos | 6 jogos com banner da Steam no fundo |
| frases favoritas | citações que eu gosto |
| top músicas | 6 faixas com player embutido do Spotify |
| links | redes sociais e projetos |

---

## como editar

### trocar a foto do perfil
substitua o arquivo em `imgs/` e atualize o `src` no `index.html`:
```html
<img src="imgs/sua-foto.jpg" alt="avatar" style="width:100%;height:100%;object-fit:cover;" />
```

### trocar músicas do Spotify
1. Abra a música no Spotify → `...` → Compartilhar → Copiar link
2. O link tem formato `https://open.spotify.com/track/XXXXXXXXXXXXXXXXXXXXXXXX`
3. Pegue só o ID (parte após `/track/`) e cole no embed:
```html
<iframe src="https://open.spotify.com/embed/track/SEU_ID_AQUI?utm_source=generator&theme=0" ...></iframe>
```

### adicionar/trocar jogos favoritos
1. Encontre o Steam App ID do jogo (na URL da página do jogo na Steam)
2. No `index.html`, atualize o `--banner` e as informações do card:
```html
<div class="game-card" style="--banner: url('https://cdn.akamai.steamstatic.com/steam/apps/SEU_APP_ID/header.jpg')">
  <div class="game-rank">nº 01</div>
  <span class="game-name">Nome do Jogo</span>
  <span class="game-genre">Gênero · Plataforma</span>
  <span class="game-note">sua nota pessoal</span>
</div>
```

### configurar o Discord (Lanyard)
1. Entre no servidor do Lanyard: [discord.gg/lanyard](https://discord.gg/lanyard)
2. O Discord ID já está configurado no `index.html`:
```js
const DISCORD_ID = '1213505861952212993';
```
3. A presença atualiza automaticamente a cada 15 segundos

### editar frases favoritas
no `index.html`, encontre os blocos `.quote-block`:
```html
<div class="quote-block">
  <p class="quote-text">sua frase aqui</p>
  <span class="quote-author">Autor</span>
</div>
```

### modo claro / escuro
o botão `◐` fica fixo no canto inferior direito. a preferência é salva automaticamente no navegador via `localStorage`. para mudar o tema claro, edite as variáveis em `style.css`:
```css
:root.light {
  --bg: #f5f5f3;
  --surface: #ffffff;
  /* ... */
}
```

---

## jogos configurados

| # | jogo | steam app id |
|---|---|---|
| 01 | Fallout: New Vegas | 22380 |
| 02 | Ultrakill | 1229490 |
| 03 | Persona 5 Royal | 1687950 |
| 04 | Signalis | 1262350 |
| 05 | Baldur's Gate 3 | 1086940 |
| 06 | Dead by Daylight | 381210 |

---

## músicas configuradas

| # | título |
|---|---|
| 01 | Begin Again |
| 02 | Femme Fatale |
| 03 | Clareza |
| 04 | Panoramic Feelings |
| 05 | Beginning of the Dream |
| 06 | Full Speed Ahead |

---

## links configurados

| plataforma | usuário / link |
|---|---|
| Twitter / X | [@quartz7k](https://x.com/quartz7k) |
| GitHub | [Lucy7x](https://github.com/Lucy7x) |
| Instagram | [@quartz7k](https://www.instagram.com/quartz7k/) |
| Spotify | [perfil público](https://open.spotify.com/user/31wejol2227edlq4dcnqc5uuspfu) |
| Discord | [quartz7k](https://discord.com/users/1213505861952212993) |
| Straw Page | [quartz7k.straw.page](https://quartz7k.straw.page/) |
| Projeto | Meridiana *(link a adicionar)* |

---

## tecnologias

- HTML / CSS puro — sem frameworks
- [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) via Google Fonts
- [Lanyard API](https://api.lanyard.rest) — presença do Discord em tempo real
- [Discord CDN](https://cdn.discordapp.com) — ícones de jogos
- [Steam CDN](https://cdn.akamai.steamstatic.com) — banners dos jogos
- Spotify Embed API — players de música

---

## deploy

hospedado via **GitHub Pages** em  
[`https://Lucy7x.github.io/V1`](https://Lucy7x.github.io)