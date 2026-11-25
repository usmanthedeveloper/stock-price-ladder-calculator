# stock-price-ladder-calculator

Simple one-page HTML/JS calculator showing your stock position's value and P/L at price steps up or down, with optional live prices and £ conversion.

## Use

Open `index.html` in a browser. No build or server needed.

- Enter quantity, current price and (optionally) the price you bought at.
- Pick a step (1, 2, 5, 10… or a custom number) as a price amount or percent.
- The table shows price, position value and gain/loss at each step.
- Tick **Show £** to convert values to GBP using a live USD→GBP rate.
- Inputs are saved in your browser until you press **Clear**.

## Live prices (optional)

Copy `config.example.js` to `config.js` and add your [Polygon / Massive](https://polygon.io) API key.
The page then shows a Symbol box that fetches the latest price (including extended hours),
cached and refreshed every 5 minutes. Without a key, just type the price in.

`config.js` is git-ignored so your key is never committed.
