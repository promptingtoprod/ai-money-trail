# AI Money Trail · Free Prompt

Paste the prompt below into Claude Code (or a similar AI coding assistant) in an empty folder to build a standalone page, or inside a project you already have to add it as a tab. It interviews you first, then builds.

**The starting prompt is free.** Your chosen AI coding assistant may require a paid plan or usage charges. This document provides instructions for creating software; it is not a finished application.

### Important disclaimer

This is an educational tool for exploring publicly available information about AI infrastructure spending, revenue, contracts and investment timing.

It is **not financial, investment, tax or legal advice**. It does not recommend buying, selling or holding securities, assess whether an investment is suitable for you, or predict stock prices or whether an AI bubble will burst.

Company figures may be delayed, revised, incomplete or defined differently. Capital-spending guidance is not actual expenditure, and contractual commitments are not guaranteed future cash receipts. All financial-model results are hypothetical, depend on stated assumptions and are not reported company losses or forecasts.

The prompt is provided **as-is, without warranty**. AI-generated software may contain calculation, security or data-quality errors. Review the generated code, test the calculations and verify material figures against original disclosures before relying on the results. You remain responsible for how you use the generated application and any financial decisions you make.

Company names are used for identification and comparison only. Their inclusion does not imply sponsorship, affiliation or endorsement.

Do not put personal financial records, credentials or confidential information into the coding assistant. The finished application may run offline, but the AI coding service used to build it may process project content under its own terms and privacy policies.

---

## The prompt

Build me a page called **AI Money Trail** that follows the money behind the AI build-out using only public company filings and official announcements, with a source link on every reported company figure.

Before writing any code, ask me one question at a time until you know:

1. Whether this is a standalone HTML page or a tab inside an existing project.
2. Which companies to track as **spenders** (suggested: the large cloud and platform companies), as **chip and hardware sellers**, and as **renters** (AI labs that rent computing). Let me add or remove any.
3. Whether the data lives in one JSON file I can edit by hand (default: yes).
4. Whether the finished page must work offline with no outside calls (default: yes).
5. Which country to add a local section for, in its own currency (default: none).
6. Whether to use the default warning triggers for the Tracker's three things to watch (listed under Tab 2), or change any.

Then build it to these rules.

### Data rules, never break these

- **Never invent a number, a date or a source.** Provide a source for every figure. If you can't find one, leave the figure out or mark it "unverified". Never fill a gap from memory.
- Every company figure carries: value, unit, reporting period, source URL, source date, date last checked, and a **classification**:
  - `actual`: a reported result.
  - `guidance`: a company's stated plan or projection.
  - `commitment`: a reported agreement or obligation, not necessarily delivered or paid.
  - `estimate`: a transparently derived estimate, with methodology and underlying sources.
  - `scenario`: a hypothetical model assumption, clearly separated from company disclosures.
- Do not present an estimate or scenario as a reported fact.
- Say what each number represents. Companies define capital expenditure, infrastructure investment, free cash flow and backlog differently.
- Backlog or remaining performance obligations generally represent contracted revenue not yet recognised under the company's reporting definition. Some amounts may already have been billed or paid. Recognition timing is not necessarily cash-payment timing. Contracts may be modified, delayed or cancelled, so backlog is not guaranteed future cash.
- **Never add incompatible figures as though they were directly comparable.** If showing an approximate combined spending-guidance figure, identify the companies, periods, amounts and accounting differences. Explain that combined corporate capital spending includes expenditures beyond AI infrastructure. Never show a plan as money already spent. If a meaningful total cannot be constructed, show the figures separately.
- Figures in US$ billions unless marked; identify fiscal years that differ from calendar years.
- **No personal data anywhere:** no names of private individuals, account numbers, personal holdings, emails, API keys or passwords in the code or data file. Use synthetic data during development.
- **If this is a tab inside an existing project,** don't read, show or send any of that project's other data. The tab reads only its own JSON file, and the export contains only this tab. If you use helpers or subagents for research, tell them not to open the project's files.
- **If outside calls are allowed** (question 4), send only ticker symbols, nothing else.
- Use plain text company names; don't copy company logos or branding into the page.
- A company name, chart colour or status indicator must never imply a buy, sell or hold recommendation.
- The finished page must display an educational disclaimer and the date the figures were last reviewed.

### The look

- Dark theme. Title: **"AI Money Trail · follow the money behind the AI build-out"**.
- Under it, one short line per tab explaining what it answers:
  - **Overview:** the picture in ten seconds.
  - **Tracker:** who is spending, and what supports it.
  - **Where the money goes:** who pays whom, top to bottom.
  - **Where it's built:** data centres, power deals, chip commitments.
  - **Delay machine:** how timing and useful life change the payback.
- Then the line: "Figures in US$ billions · updated [date] · educational, not advice", followed by the tab strip.
- Rounded cards with a thin coloured top border.
- Big numbers in colour: orange = money going out, blue = money coming in, green = reported or on time, red = short or late.
- One **data-status dot** on every item: green = reported for its latest period; amber = announced commitment, guidance or verification pending; grey = not disclosed or unavailable. These indicate reporting status, not financial safety. A legend sits under each section title.
- Classification chips beside numbers: `PLAN = GUIDANCE`, `SPENT SO FAR = ACTUAL`, `COMMITMENT`, `ESTIMATE`, `SCENARIO`, `NOT LIKE FOR LIKE`.
- Draw bars and rings as plain HTML/SVG, with no chart library.
- Keep cards short: the number, its chips and one line. Put definitions and long notes in folded sections.

### The five tabs

#### 1. Overview (the default view)

- Four tiles:
  - **Planned for this year:** approximate selected-company spending guidance, using the midpoint of a range and saying so, with a short note that it includes non-AI spending and is not like for like. Keep the tile short; put the companies, reporting periods and definitions in a folded "How this is counted" under it.
  - **Spent so far:** only companies reporting a year-to-date figure; name those omitted.
  - **Selected quarterly cloud sales:** only segments that are cloud alone; name wider segments and leave them out of the sum.
  - **Next results:** company and date, only dates officially announced by the company.
- A full-width strip marked **"ILLUSTRATIVE MODEL · NOT A REPORTED FIGURE"**, with the Delay machine's two headline answers for the Planned-for-this-year total: net cash needed each year **on time** (years 1–5) and **two years late** (years 3–5), plus a link to the Delay machine.
- Three cards in a row:
  - A ring of **who is spending this year**, with planned spending per company and shares.
  - A ring of **who collects the rent**, using latest-quarter selected cloud sales.
  - **Selected supplier revenue measures** as horizontal bars, showing chip, foundry and memory manufacturers' data-centre sales, each with its own reporting period and a note that these figures must not be added together.

#### 2. Tracker

- **Three things to watch**, across the top as indicators:
  - Spending plans.
  - Cash after spending.
  - Financing.

  Each indicator describes only defined evidence in reviewed disclosures:
  - **Grey:** insufficient information or not assessed.
  - **Green:** no specified warning trigger found in reviewed disclosures as of the stated review date. This does **not** mean the company is safe or risk-free.
  - **Amber:** a documented development matching a pressure trigger.
  - **Red:** a documented event matching a serious warning trigger.

  Default triggers (confirm or change them in question 6), each counted only when a filing or official company statement reports it:
  - **Spending plans.** Amber: a company lowers its spending guidance or delays an announced project. Red: a project is cancelled for lack of demand.
  - **Cash after spending.** Amber: free cash flow negative over the latest 12 months. Red: a company says it cannot fund planned spending from its own cash.
  - **Financing.** Amber: a new large debt or equity raise to fund the build-out. Red: a reported missed payment or default on project financing.

  Clicking an indicator shows the source, date, exact trigger and reason in one sentence. Never infer an absence of risk from missing information. State on-screen that these indicators are educational summaries, **not buy, sell or hold signals**.

- **Money out:** one row per spender, with a horizontal orange bar showing spending so far against a grey track labelled "plan $X"; period and latest quarter underneath; smaller chips showing what the company has said about server accounting lives, next year's guidance and trailing 12-month free cash flow, where officially reported. Explain differences in company definitions. Include a folded "How this is counted" section. If a company provides only quarterly figures, display the quarter without inventing year-to-date progress.

- **Money in:** one card per cloud seller showing:
  - Company name, reporting segment and quarter.
  - Revenue and growth.
  - Blue bar: **Segment revenue**.
  - Orange bar: **Segment operating expenses**.
  - Green bar: **Segment operating income**.

  Calculate operating expenses as **segment revenue minus segment operating income** only when both figures are reported for the same segment and period and the calculation is valid under that company's reporting definition.

  Label this clearly as **accounting operating expenses, not cash running costs**. It may include depreciation, amortisation and other noncash expenses. It is not a direct measurement of the cash required to operate AI infrastructure, nor a measure of free cash flow. If the reported figures are insufficient for a sound calculation, omit the operating-expenses bar.

  Include a boxed **Future contracted revenue** measure (backlog), with its timing only as the company states it, for example "about 30% expected to be recognised within 12 months". Add `COMMITMENT` and `NOT LIKE FOR LIKE` chips plus a folded "Customers named, sources" section.

  Under the cards: "Backlog represents contracted revenue not yet recognised under the company's definition. Some amounts may already have been billed or paid. It is not a cash-payment schedule or guaranteed revenue."

- **The log:** table with date, company, kind (spending / orders / chips / financing), amount, what happened, source link, status ("Reviewed disclosure · reviewed [date]" or "Unverified") and a coloured data-status dot. Newest first, "Show N older" button, nothing automatically deleted.
- Footer: company investor-relations links, folded "What the terms mean" and "Change history".

#### 3. Where the money goes

Create a top-to-bottom conceptual map with labelled arrows between rows.

Label the entire illustration: **"Illustrative economic relationships, not a trace of any individual customer's payment."**

1. **You:** consumer plans with reported prices, plus "Businesses and apps pay per use".
   - Arrow: *subscriptions and usage fees*.

2. **The AI labs, and which cloud they pay:** one card per lab with revenue as officially stated and named cloud contracts.
   - Arrow: *rent for computing*.

3. **The cloud companies:** one column per company with latest sales.
   - Arrow: *spends on*.
   - Card: **What it spends on**: chips and servers, buildings, land and leases, power. Use the company's own allocation if disclosed; otherwise show "allocation not disclosed" alongside reported capital spending.
   - Arrow: *who gets paid, and by whom*.

4. Three cards side by side:
   - **4a. Chips, memory and storage.**
   - **4b. Power companies.**
   - **4c. Builders and landlords.**

   Each item shows "Payer → Payee", the agreement or transaction, and a source. Do not imply that a particular subscription payment can be traced directly to a specific supplier.

   - Arrow: *chip makers pay the factory*.

5. **The factory:** foundries that manufacture the chips.

Then show a folded **"The same relationships as a table, with sources"** section.

Only sourced figures; anything else is marked as illustration. Never chain figures from different periods into a single payment total. Do not double-count the same contract or expenditure at multiple levels of the diagram.

#### 4. Where it's built

- **What the money buys:** per spender, compare short-lived assets (chips, servers) with long-lived assets (buildings) only where the company discloses a meaningful split. Otherwise show "no comparable split disclosed".
- **The biggest builds:** project, location, companies involved and intended customers where known, announced cost, announced power capacity, status (announced / building / running), latest official update, source and review date. Announced capacity is not operating capacity.
- **My own country:** based on question 5, with local currency, source and exchange-rate date where conversion is necessary.
- **Power deals:** buyer, deal, size in MW or GW and expected timing.
- **Chip and cloud agreements:** buyer → seller, size, status (signed / term sheet / announced), source and disclosure date. Explain that an AI lab's cloud agreement and the cloud company's associated backlog can refer to the same contractual relationship and must not be counted twice.
- **Lab commitments and revenue:** what AI labs have reportedly committed to, compared with revenue disclosed by the labs. Explain that commitments can span multiple years, have different contractual terms, and may change. Do not treat the figures as direct measures of insolvency risk or guaranteed future cash needs.

#### 5. Delay machine

**This is an illustrative mathematical model, not a company forecast. Display that prominently.**

- Preset buttons:
  - **On time.**
  - **1 year late.**
  - **2 years late.**
  - **2 late, lasts 10 years** (first cash year 3, final earning year 10).
  - **Scale to selected spending guidance ($ total).**
  - **$100B example.**

- A **Delay assumption** dropdown:
  - "Fixed final earning year, delay removes payments" (default).
  - "Useful life shifts with the delay".

  Show the selected assumption beside every result.

- Two sliders:
  - **First cash flow arrives in year N.**
  - **Assumed economic useful life (final earning year).**

- Bar chart, years Y1 to Y12:
  - Each productive year shows assumed annual net cash received and what that payment is worth today.
  - Years before first cash flow say "waiting".
  - Years after the final earning year say "outside model".

- **Required annual net cash flow**, displayed prominently in orange:

  `Investment cost ÷ sum of discount factors for productive years`

  Explain that this is the equal annual net cash flow needed to break even under the model assumptions, not a forecast of what customers will pay.

- An assumptions grid:
  - Investment amount and when paid.
  - Required return: 10% nominal (assumption).
  - First and final cash-flow year.
  - Number of productive years.
  - Delay policy.
  - What net cash flow means: after operating cash costs, taxes and upkeep required by the model; not accounting revenue or operating income.
  - Residual value: zero.
  - Result: net present value, not reported accounting profit or an investment forecast.

- **Paid today** (red bar) against **Worth today** (green bar): the upfront investment versus the discounted value of the assumed payments, with the gap clearly labelled **"Hypothetical present-value shortfall under these assumptions, not a reported company loss."**

- When scaling the $100B example to selected corporate spending guidance, **do not confuse two different scenarios**:
  - **Proportional scale:** retain the $100B example's annual-payment-to-investment ratio.
  - **Initially break-even scale:** assume the selected investment amount would have broken even with five on-time annual payments, then remove the first two payments under the fixed-final-year scenario.

  Clearly identify which baseline is used. The approximately −$334B result belongs to the second scenario, not a direct proportional scaling of the $30B-per-$100B example.

- A **"For scale only"** strip comparing the hypothetical amount with selected reported operating income, accompanied by a note that these are different accounting and economic measures and cannot validate the model.

### Checks before you say it's done

- Unit tests for the maths. At a 10% assumed required return:
  - $100B investment and $30B a year gives:
    - +$13.72B for years 1–5.
    - +$3.39B for years 2–6 and −$6.01B for years 3–7 (these two use "Useful life shifts with the delay").
    - −$38.34B for years 3–5.
    - +$32.27B for years 3–10.
  - The yearly payment needed per $100B invested over five years is approximately $26.38B.
  - For a $730B investment, years 1–5 require approximately $192.6B a year to break even; years 3–5 require approximately $355.2B a year.
  - With the fixed final earning year, $730B paid today and approximately $192.57B a year arriving only in years 3–5 is worth approximately $395.78B today, producing a hypothetical net-present-value shortfall of approximately −$334.22B.
  - Verify that proportional scaling of the $30B-per-$100B example instead produces approximately −$279.9B. Never label these two scenarios as identical.
- Test that every reported company figure in the data file has a source URL and review date. Hypothetical values instead need clearly stated assumptions and reproducible calculation logic; never create fake source URLs for scenarios.
- Test that no segment operating-expense estimate is displayed as direct cash running costs.
- Test that the green tracker status never appears merely because no information was found.
- Test that no approximate combined spending figure is labelled AI-only or money already spent.
- All text from the data file is HTML-escaped. Source links open in a new tab with `rel="noopener noreferrer"`. The export loads no outside scripts or fonts and contains no personal data.
- No horizontal scrolling at 400px wide; text at least 12px; source links usable on a phone.
- A one-file export with no edit controls so it can be shared.
- Include the following visible line on every tab:

  **"Public information for education only. Not financial advice. Hypothetical results are not forecasts or reported company losses."**

- Add an expandable **"Data, modelling and software limitations"** section covering:
  - Figures may be outdated, incomplete or revised.
  - Accounting measures and reporting periods may differ between companies.
  - Model results depend on assumptions and are not company valuations or investment recommendations.
  - The generated application is provided without warranty and needs review.
  - The creator is not affiliated with companies solely because they are mentioned.
  - No trading, brokerage connectivity or personalised investment recommendations are offered.
- Add a README that explains data updates, sources, assumptions, calculation methods, privacy, offline behaviour, code review and known limitations.
- Show me the page in the browser before you call it finished.

---

## Tips

- Refresh the data after each company's quarterly results. Check summaries against the original filing; secondary reports can misstate numbers or omit important qualifications.
- The hard part is labelling, not code: which numbers may be added together and which may not. When in doubt, show them separately.
- Start with a small, verified dataset rather than filling all tabs with weakly sourced information.
- Keep changes traceable through a review date and source history.
- Before sharing the generated software, review its code, dependencies, data-processing behaviour and calculations. Do not publish private files or secrets.

---

## Disclaimer for redistribution

This prompt is supplied free of charge for educational use and is provided as-is, without warranties or guarantees of accuracy, reliability, security or fitness for a particular purpose. It is a set of instructions, not a finished or certified financial application.

The information and software it helps generate are intended for independent educational research, not financial, investment, tax or legal advice. They do not recommend securities or provide personalised investment recommendations. Models are illustrative; company figures may be incomplete or change over time. Users must independently verify data, review generated code and validate calculations before relying on any results.

Use of third-party AI coding services may incur fees and may involve processing project contents under those providers' terms. The finished software's privacy and security properties depend on its implementation and configuration.

Company names and references are informational and do not imply affiliation, sponsorship or endorsement.
