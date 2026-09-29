# senales-grafico en la constelación

Declaración de este repo para el grafo de proyectos de la casa (lo lee el
observatorio interno de la casa, que documenta el formato). Repo público:
solo superficies públicas.

| campo | valor |
|---|---|
| id | senales-grafico |
| clase | app |
| qué | la vitrina del punto de entrada: `grafico.html` dibuja en el navegador la señal del tablero (velas del perpetuo paradas en la vela que confirmó, cuello, stop, objetivo) desde los parámetros del enlace 📈 de Telegram |
| dónde | GitHub Pages → `https://yvalenta.github.io/senales-grafico/grafico.html` |
| servicio | `—` (página estática) |
| atiende | quien abre el 📈 desde el grupo de Telegram; el contenido lo deposita tablero (`bin/publicar_grafico`) |
| contexto | `README.md` |
| visibilidad | público: `github:yvalenta/senales-grafico` |

## Aristas

| a | b | tipo | por | medición |
|---|---|---|---|---|
| senales-grafico | github | publica | GitHub Pages sirve `https://yvalenta.github.io/senales-grafico/` | `http https://yvalenta.github.io/senales-grafico/grafico.html 200` |
| senales-grafico | tablero | mira | la página que este repo sirve la escribe y prueba tablero (`web/grafico.html`), que la copia acá con su commit en la cabecera | `—` |
| senales-grafico | binance | consume | el navegador de quien abre la página pide las velas a `fapi.binance.com` | `http https://fapi.binance.com/fapi/v1/ping 200` |
