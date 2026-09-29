# senales-grafico — el punto de entrada, en el gráfico

Una sola página estática, [`grafico.html`](grafico.html), servida por GitHub Pages en
`https://yvalenta.github.io/senales-grafico/grafico.html`.

Dibuja el punto de entrada de una señal del tablero de la casa: pide al navegador las
velas del perpetuo de Binance (`fapi.binance.com`, CORS abierto) del plazo de la señal,
las deja paradas en la vela que confirmó la ruptura y marca el cuello (la entrada, desde
su pivote), el stop y el objetivo, con un botón para saltar a TradingView. Se abre desde
el enlace 📈 del grupo de Telegram, que trae los parámetros en la URL:
`?par=ETHUSDT&tf=1h&vc=<cierre de la vela, epoch s>&e=<entrada>&s=<stop>&o=<objetivo>&d=up|down&c=<cierre>`.
Sin parámetros, o con uno inválido, no pide nada y lo dice.

Un enlace de TradingView no puede hacer esto: su URL solo acepta par e intervalo, abre
siempre en la última vela y no hay parámetro de fecha ni de niveles. Por eso existe esta
página.

## Qué es y qué no es

- **Es la vitrina**: la fuente de verdad es `web/grafico.html` del repo `tablero`
  (privado), con sus pruebas. La copia de acá se reemplaza entera con
  `bin/publicar_grafico` de tablero y lleva en su cabecera el commit del que salió; no se
  edita acá.
- **No es una señal ni un consejo**: la página solo dibuja los números que vienen en la
  URL (recalcula el cuello sobre las velas y avisa si no coincide; stop, objetivo y cierre
  se muestran como llegan). Esto mide, no aconseja.
- **No guarda nada**: no hay servidor propio; el navegador habla solo con
  `fapi.binance.com` y el CDN de Lightweight Charts (fijado por versión y SRI).

El gráfico lo dibuja [Lightweight Charts](https://github.com/tradingview/lightweight-charts)
© TradingView, Apache-2.0.
