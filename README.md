# Nick's Timber

## Mill Job Estimator (`mill-estimator.html`)

A single-page calculator for working out what it costs to run a job through the mill and what to charge for it. Open the file in any browser; it needs no install or internet connection, apart from the web fonts.

**Using it**

1. Pick the timber and enter the log volume (m³), any extra handling time and delivery miles.
2. Choose whether the logs are the customer's (milling only) or ours (log cost included), and tick kiln drying if needed.
3. Read off the cost, the selling price (ex and inc VAT), the profit, and the rates per mill hour, per m³ and per cubic foot.
4. "Same job, every timber" runs the same job through every timber in the list for comparison.

**How the cost is built**

| Cost | Worked out from |
| --- | --- |
| Wages | total mill hours × crew hourly rates + employer on-costs % |
| Electric | sawing hours × (motor kW × load % + other kit kW) × pence per kWh |
| Diesel | sawing hours × litres per hour × price per litre |
| Blades | sawing hours × (blade price ÷ sharpens per blade + sharpening cost) ÷ hours per sharpen for that timber |
| Mill wear | total hours × (mill price − resale value) ÷ years ÷ mill hours per year |
| Yard overheads | total hours × yearly overheads ÷ mill hours per year |
| Consumables, kiln | per sawn m³ |
| Logs (own timber only) | log m³ × log price |
| Delivery | miles × £ per mile |
| Metal & breakdown allowance | % of everything above |

Mill hours = log volume ÷ the timber's cutting rate + its set-up time + any extra handling time.
Selling price = cost ÷ (1 − margin %), never below the minimum job charge.

All settings start as example figures. Replace them with real wages, tariffs, bills and timed cutting rates. Settings save in the browser; use "Back up or move settings" to copy them to another device.
