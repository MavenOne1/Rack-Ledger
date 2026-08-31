# Rack Ledger

A one-page app for tracking which pallets are sitting in which rack bins. Runs entirely in the browser, no server or database, so it can be hosted free on GitHub Pages and opened on any phone in the warehouse.

## What it does

- **Rack chart** — every aisle drawn as an elevation, racks running left to right, bins stacked top to floor the way the racking actually stands. Filled bins show the job number, description, and shipment. Tap a bin to see everything in it.
- **Put away** — job number, shipment number, description dropdown, piece count, operator initials, bin, and notes. "Next open" jumps to the first empty bin.
- **Inventory** — filter by status or description, sort by date, bin, or job.
- **Search** — type a job number, shipment number, or bin and the chart highlights the hits and greys out the rest.
- **Print** — the chart prints landscape, one block per aisle, for the wall or a clipboard.
- **Move / Ship out / Delete** — from the bin popup.
- **Backup** — download a JSON backup or a CSV for Excel; load a backup onto another device.

## Putting it on GitHub Pages

1. In GitHub, create a new repository. Public is fine; the app holds no data in the repo.
2. Upload `index.html` (and this README if you want) to the root of the repo.
3. Go to **Settings → Pages**.
4. Under **Source**, pick **Deploy from a branch**, choose branch `main` and folder `/ (root)`, then **Save**.
5. Wait a minute, then reload the Pages settings screen for the live URL. It will look like `https://yourname.github.io/rack-ledger/`.
6. Send that link to the crew. On the phone, open it, tap Share, then **Add to Home Screen** — it opens like a normal app after that.

To make changes later, edit `index.html` in GitHub and commit; the site updates in about a minute.

## Set up the rack layout first

Open **Setup**, enter your aisle letters, racks per aisle, and bins per rack, then save. It ships set to one aisle named R with 6 racks of 4 bins.

Bin codes are the aisle letter followed by a number that counts straight through the aisle, left to right and top to bottom. `R1` is the top bin of the first rack and `R4` is the floor bin under it; `R5` starts at the top of the second rack, so the aisle runs `R1` through `R24`. Add a second aisle called B and it numbers `B1` through `B24`. The description dropdown is editable in Setup too.

Have one person set the layout, then use **Download backup** on that device and **Load a backup** on the others so everybody starts from the same rack map.

## How the saving works

Each device stores its own copy in the browser. That is what makes it free and offline-capable, but it also means two phones do not see each other's entries. Options:

- **One device of record.** Put-aways get entered on a shared tablet or the office PC. Everyone else opens the same link read-only to look things up, and the chart gets reprinted each morning.
- **Pass backups around.** Download a backup at the end of a shift, load it on the next device.
- **Add a shared backend later.** If you outgrow this, the same screen can point at a shared database instead, with no change to how the crew uses it.

Clearing browser data or "clear website data" on the phone will erase the ledger on that device, so take a backup periodically.
