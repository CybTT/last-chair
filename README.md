# Last Chair

A pixel-art game of musical chairs. Four guests, one chair too few, three rounds.

Walk while the light is green, take a seat the moment it turns red. Sit too
early and you are out; sit too late and a rival takes the last chair.

## Play

The game is a static site — no build step, no dependencies.

```sh
cd dist && python3 -m http.server 8000
```

Then open http://localhost:8000.

## Controls

| Input | Action |
| --- | --- |
| `SPACE` / tap **SIT** | Take a seat |
| `ESC` / **Ⅱ** | Pause and resume |

## Layout

- `dist/index.html` — markup
- `dist/style.css` — pixel-cabinet styling and the responsive layout
- `dist/game.js` — game loop, rival reaction model, sprite atlas handling
- `dist/assets/` — room and character art, bitmap fonts

Rival reaction times come from `rivalDelay()`: each opponent has its own base
and spread, every round shaves 18ms off, and nobody can ever move before the
light turns red.
