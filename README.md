# Nick's Timber

## Mill Job Estimator (`mill-estimator.html`)

A single-page calculator for working out what it costs to mill a job from sawn boards (mainly joinery redwood) and what to charge for it. Open the file in any browser; it needs no install or internet connection, apart from the web fonts.

**Using it**

1. Pick the timber, enter the finished linear metres, the sawn board section (mm), any extra handling time and delivery miles.
2. Choose whether the boards are ours (timber cost included) or the customer's (milling only).
3. Read off the cost, the selling price (ex and inc VAT), the profit, and the rates per linear metre, per m³ of board and per machine hour.
4. "Same job, every timber" runs the same job through every timber in the list for comparison.

**How the cost is built**

Board needed = finished lm ÷ (1 − the timber's waste %), and its volume = board lm × thickness × width.
Machine hours = board lm ÷ (feed speed m/min × 60 × feed efficiency %) + the timber's set-up time + any extra handling time.

| Cost | Worked out from |
| --- | --- |
| Sawn boards (our timber only) | board m³ × the timber's £/m³ |
| Wages | machine hours × crew hourly rates + employer on-costs % |
| Electric | running hours × (motor kW × load % + extraction and other kW) × pence per kWh |
| Diesel | running hours × litres per hour (forklift) × price per litre |
| Cutters | running hours × (cutter set price ÷ sharpens per set + sharpening cost) ÷ hours per sharpen for that timber |
| Machine wear | machine hours × (machine price − resale value) ÷ years ÷ machine hours per year |
| Overheads | machine hours × yearly overheads ÷ machine hours per year |
| Consumables | per m³ of board |
| Delivery | miles × £ per mile |
| Breakdowns & rejects allowance | % of the milling costs (not the timber) |

Selling price = cost ÷ (1 − margin %), never below the minimum job charge.

All settings start as example figures. Replace them with real wages, tariffs, bills, timber prices and timed feed speeds. Settings save in the browser; use "Back up or move settings" to copy them to another device.
