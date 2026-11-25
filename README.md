# stock-price-ladder-calculator

Simple one-page HTML/JS calculator showing your stock position's value and P/L at price steps up or down, with optional live prices, price alerts and £ conversion.

## Use

Open `index.html` in a browser. No build or server needed.

- Enter quantity, current price and (optionally) the price you bought at.
- Pick a step (0.5, 1, 2, 5, 10… or a custom number) as a price amount or percent.
- The table shows price, position value, change vs now and P/L vs your buy price at each step.
- Tick **Show £** to convert values to GBP using a live USD→GBP rate (free ECB rates, no key needed).
- Use **Summary size** to enlarge the value / cost / P/L line.
- Inputs are saved in your browser as you type, until you press **Clear**.
- **Clear** stores the current inputs in **History** (last 5, newest first) so you can restore them.
- Ladder, Alerts, Settings and History are collapsible sections; only Position is always shown.

## Live prices (optional)

Copy `config.example.js` to `config.js` and add your [Polygon / Massive](https://polygon.io) API key.
The page then shows a Symbol box that fetches the latest price (including extended hours).

- Fetches once on page load and auto-refreshes (Off / 1–30 min, default 5) with a matching cache to save API calls.
- **Get price** (or Enter in the Symbol box) always fetches fresh and resets the cache.
- Without a key, the Symbol box is hidden and you type the price in yourself.

`config.js` is git-ignored so your key is never committed.

## Price alerts

Set **Alert above** and/or **Alert below** a price. When a live price crosses the level,
a 3-second siren plays and a message shows what triggered. Alerts are one-shot: the level
clears after it fires. Use **Test sound** to hear it.

Notes: browsers only allow sound after you click the page once, alerts need live prices
(a Polygon key), and the page must stay open in a tab.
