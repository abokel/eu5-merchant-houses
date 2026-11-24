# Merchant Houses: Corporations & Chartered Companies (EU5 mod)

A Europa Universalis V mod (built for game version 1.4.x) that makes playing a bank, the Hanseatic League or a merchant republic a full playstyle:

- Incorporate as a **Corporation**, a new government type led by a **Governor** and a board of **Directors**.
- Win **Corporate Charters** inside other countries, petition them for rights, and build up **Control**.
- Turn a host into a **Corporate Protectorate**, then **absorb** it.
- **Land** your company: foreclose on debtors, claim your estates, or found a **Presidency** in India or the East Indies and become an independent **Chartered Company**.
- Family ties: when a member of your ruling family rules a host, you control it faster and can merge with it sooner.

> Status: untested in-game. If something breaks, check `Documents/Paradox Interactive/Europa Universalis V/logs/error.log`. See the walkthrough for how to play.

Separate from, and compatible with, Colonial Mandates & Landed Trade Companies (it uses its own `mh_` names and its own Presidency buildings).

## Features

### The Corporation government
- **Incorporate the Company** (decision, Economy): available to countries with the Banking Family, Merchant Republic or Hanseatic Merchant Federation reform. Costs 100 gold.
- Titles: the ruler is the **Governor** (Governor-General at kingdom and empire rank, and for a Chartered Company), the heir is the **Deputy Governor**, a regent is the **Acting Governor**, and cabinet members are **Directors**.
- Rank names: Counting House, Company, Great Company, Imperial Company, or Chartered Company.
- **Board Election**: the board elects a Governor for life from three candidates. Administrative skill counts double.
- **Board confidence** (0-100, starts at 60): judged on your monthly balance (income minus expenses), smoothed over a few months. +1 per month after 2 or more profitable months in a row (+0.5 more with a margin of a fifth of income), -1 after 2 or more losing months, -0.5 at war, -3 in bankruptcy. Buying buildings or repaying loans does not count against you. Big actions need a minimum and cost some.
- **Vote of No Confidence**: below 15, the board moves to replace the Governor with its ablest Director. You can accept, buy them off (12 months of income), or under the Family Firm, close ranks.
- **Pay a Dividend** (decision): 6 months of income for +20 confidence, every 2 years.
- **Company Ledger** (decision): shows board confidence and how many stakes and protectorates you hold.
- Reforms (pick one): **Family Firm** (family members get +60 in board elections, family ties abroad count double) or **Joint-Stock Board** (+10% cabinet efficiency, cheaper loans, confidence recovers toward 50).
- Merchant republic and Hanseatic privileges carry over as the **Merchant Corporation** and **Hanseatic Corporation** reforms.

### Charters and Control (the pseudo-estate)
- **Request Corporate Charter** (diplomatic relation, Economy): ask a landed country to let your company operate there. One company per host.
- While the charter lasts, your **Control** over the host grows every month: +0.4 base, +0.2 Trading Rights, +0.2 Levy Rights, +0.3 Tax Farming, +0.4 if they owe you money, +0.4 for family ties (+0.8 with Family Firm), +0.5 if they are your protectorate. Without a charter it falls by 1 per month.
- Hosts show their tier as a modifier: Company Concession, Influence (25+), Grip (50+), Dominion (75+). From 50, the host also suffers **Corporate Dominance** (rebels, separatism, legitimacy loss).
- **Petitions** (need board confidence 25 and a charter):
  - **Trading Rights**: build **Factor's Houses** there. Control +5.
  - **Levy Rights**: build **Company Barracks** there (recruit regiments, draw manpower and sailors). Control +5.
  - **Tax Farming**: receive 10% of their tax and trade income every month. Control +10.
  - **Land Grant**: a **Company Estate** in a location you choose, every 2 years. Control +5.
- Hosts accept more readily when they owe you money, are broke, are at war (levies), share your ruling family, or are already under your control.
- **Extend Credit**: lend a country six months of its income (at most half your treasury) for 60 months. Control +3 if you hold its stake.
- The host can revoke the charter at any time, unless it is your subject: you lose every right and 25 control. AI hosts at 60+ control may do it on their own.
- A host that revokes gives you the **Enforce Charter** casus belli for 10 years.
- Peace terms in any war you win against a landed country: **Restore Charter** (charter back, +25 control, +10 board confidence; 25 war score, 10 with Enforce Charter) and **Demand Company Rights** (Trading Rights, Levy Rights and Tax Farming, +10 control; 20 war score, 10 with Enforce Charter).
- Petition, protectorate, absorb and land actions show your exact current control over the host in their tooltip.

### Protectorates and absorption
- **Declare Corporate Protectorate**: 50 control, board 50, and your company must own land. The host becomes a subject that follows your foreign policy. Board -10.
- **Absorb Host**: 100 control over your protectorate, or 75 control if a member of your ruling family sits on their throne. Board 60, costs 20. A landless company becomes landed.

### Landing
- **Foreclose on Land**: a debtor clears every loan it owes you by handing over one location. Board 30, gives +5.
- **Claim Company Land**: take one of your Company Estates outright. 50 control, board 40, costs 10.
- **Found a Presidency**: in South or Southeast Asia, turn a Company Estate into your own land and become an independent **Chartered Company**. 25 control, board 40, costs 10. Use it again for more Presidencies.
- A landless company (a bank) becomes a normal landed country the first time it gains land, like the vanilla Japanese clan conversion.

### Chartered Company
- Reform: +15% merchant power, +10% merchant capacity, +50% levies from other cultures, +15% levy size, +25% garrison size.
- Gets its own **Presidency** buildings in South and Southeast Asia: Headquarters (placed automatically), Garrison, Harbor, Local Venture, Residency and Governance, with the same local effects as the vanilla trade company buildings.
- Stays independent: it is not anyone's subject.

## Installation
1. Copy this folder into `Documents/Paradox Interactive/Europa Universalis V/mod/` (name it `MerchantHouses`).
2. Enable it in the EU5 launcher playset.

## Notes
- The AI never incorporates; corporations are a player path. AI hosts do grant charters, accept or refuse petitions, and may revoke charters.
- Two vanilla files are overridden to add the titles: `in_game/common/customizable_localization/country_ranks.txt` and `character_title.txt`. Mods that change rank names or character titles will clash. After a game patch, re-copy the vanilla files and paste the blocks marked `Merchant Houses` back in.
- Board confidence and control are script variables: `mh_board_confidence` and `mh_profit_streak` on the company, `mh_control` and `mh_stake_holder` on the host.
- To allow Presidencies elsewhere, edit `mh_presidency_zone_location` in `in_game/common/scripted_triggers/mh_triggers.txt`.

## Files
| File | Purpose |
|---|---|
| `in_game/common/government_types/mh_corporation.txt` | The Corporation government type |
| `in_game/common/heir_selections/mh_corporation.txt` | Board Election |
| `in_game/common/government_reforms/mh_corporation_reforms.txt` | Family Firm, Joint-Stock Board, Chartered Company, Merchant and Hanseatic Corporation |
| `in_game/common/scripted_relations/mh_corporate_charter.txt` | The Corporate Charter relation |
| `in_game/common/country_interactions/mh_interactions.txt` | Credit, petitions, protectorate, absorb, foreclose, claim land, Presidency |
| `in_game/common/subject_types/mh_corporate_protectorate.txt` | Corporate Protectorate subject type |
| `in_game/common/building_types/mh_company_buildings.txt` | Company Estate, Factor's House, Company Barracks, Presidency buildings |
| `in_game/common/decisions/mh_decisions.txt` | Incorporate, Pay a Dividend, Company Ledger |
| `in_game/events/mh_board_events.txt` | Vote of No Confidence, AI charter revocation |
| `in_game/common/casus_belli/mh_casus_belli.txt`, `in_game/common/wargoals/mh_wargoals.txt` | Enforce Charter casus belli and war goal |
| `in_game/common/scripted_effects/mh_effects.txt` | Board, control, landing logic |
| `in_game/common/scripted_triggers/mh_triggers.txt` | Shared checks |
| `in_game/common/script_values/mh_values.txt` | Numbers shown in the Company Ledger |
| `in_game/common/on_action/mh_on_actions.txt` | Monthly board and control updates |
| `in_game/common/peace_treaties/mh_peace_treaties.txt` | Restore Charter and Demand Company Rights peace terms |
| `in_game/common/customizable_localization/*.txt` | Vanilla overrides for Governor, Director and rank titles |
| `main_menu/common/static_modifiers/mh_static_modifiers.txt` | Tax farming, dominance and control tier modifiers |
| `main_menu/common/named_colors/mh_colors.txt` | Map color |
| `main_menu/localization/english/mh_merchant_houses_l_english.yml` | English text |
