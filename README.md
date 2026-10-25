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

**Hardwood tab**

Pick the hardwood and enter the size the customer wants (e.g. 25 × 150 mm) and the finished linear metres. Each hardwood in Settings → Hardwoods has its own cost price per m³ and its own waste allowances:

- Raw width = finished width × (1 + width waste %), so 150 mm at 30% = 195 mm.
- Raw thickness = finished thickness + thickness allowance (mm, 0 by default).
- Raw length = finished lm × (1 + length waste %, 0 by default).
- Raw m³ = raw thickness × raw width × raw length. The **Copy m³** button copies this figure for the mill line.

The page then shows two things:

- **Milling charge (lump sum):** the softwood costing model run as a milling-only job on the raw stock, using that hardwood's feed speed, cutter life and set-up time, with the main profit margin and minimum job charge. A table underneath shows what's in it.
- **Estimated raw stock (m³)**, with what that stock costs at the hardwood's £/m³ shown in the note under the job.

All settings start as example figures. Replace them with real wages, tariffs, bills, timber prices and timed feed speeds. Settings save in the browser; use "Back up or move settings" to copy them to another device.

## Customer delivery calculator for Shopify (`shopify/sections/delivery-calculator.liquid`)

A theme section for the online store. Customers enter a postcode or town and see the delivery price, plus how much more they need to spend for free delivery (worked out from what's already in their basket). It uses the same rate card as the team Delivery Rates page, but only shows prices, never what a run costs us.

**Installing it**

1. In Shopify admin go to Online Store → Themes. On the theme you want, click ⋯ → Edit code. Try it on a copy of the live theme first.
2. Under Sections, click "Add a new section", name it `delivery-calculator`, delete the starter code, and paste in the whole file.
3. Save, then open Customize. Add the "Delivery calculator" section wherever you want it: a Delivery page, the basket page, or product pages.

**Changing the prices**

The prices are set in the theme editor, not in the code. Click the section to see its blocks:

- **Charge band:** "Up to X miles" and the flat charge (£ ex VAT). One block per band.
- **Free delivery:** "Up to X miles" and the minimum order (£ ex VAT) for free delivery. One block per band.
- Section settings: minimum charge, the per-mile price past the last band (blank = "please call us"), free delivery past the last band, the furthest you deliver, contact details and the wording.

The defaults are the team rates from 21 Oct 2026 (diesel 199p). When the team rates change, update the blocks to match the team Delivery Rates page.

**How it works:** the postcode or place is looked up with the free postcodes.io service (Ordnance Survey and ONS data). The road distance is the straight-line distance from the yard × 1.2, the same as on the team page. The basket total is read from the store, which shows prices ex VAT, so it compares straight against the free-delivery amounts. The customer's last postcode is remembered in their browser.

It's a guide price on the store pages; it does not add delivery at checkout.
