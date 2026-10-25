# SPL Pipe Rush

**I’ve been trying to learn Splunk’s search language outside of work, and there’s basically nothing good — old YouTube videos and huge walls of text. So I built what I wished existed, with the help of AI: a free, browser-based way to actually practise SPL hands-on, no license needed. It’s how I’m learning it myself. It’s not perfect — if you know Splunk and spot something wrong, tell me and I’ll fix it

▶ **Play it:** https://sallulah.github.io/SPL-Rush/

---

## What's inside

| Part | What you learn |
|---|---|
| **Station 1: Search basics** | Events, indexes, time ranges, the pipe, `stats`, `sort`, `table`, `eval`, `where`, `dedup`, `top`/`rare` |
| **Station 2: Investigation** | `timechart`, `chart`, `rex`, `regex`, `spath`, the eval toolkit, `eventstats`, `streamstats`, `transaction`, lookups, subsearches, `append`/`appendcols`/`join` |
| **Station 3: Knowledge objects** | Field extractions, aliases, calculated fields, event types, tags, macros, workflow actions, reports, alerts, dashboards, data models, the CIM, `tstats` |
| **Station 4: Detection** | Turning searches into alerts, trigger conditions, scheduling and indexing lag, throttling, allowlists, baselines, reading ESCU-style detections |
| **Station 5: Admin** | `indexes.conf` and retention, universal vs heavy forwarders, `props.conf` and `transforms.conf` (index time vs search time), roles and capabilities |
| **Station 6: Enterprise Security** | Notables and Incident Review, urgency (severity × priority), triage, risk-based alerting, correlation searches and adaptive response |
| **Station 7: SOAR** | Containers, artifacts, apps, assets, actions, playbooks, and what to automate vs gate behind a human |

Plus:

- **Alert Desk:** realistic SOC tickets (brute force, impossible travel, encoded PowerShell, lateral movement, beaconing, DNS tunnelling and more). You write the search, and it's graded on your results, not your exact wording.
- **Capstone investigations:** three full incidents graded on what you find, with decoys you have to rule out with evidence.
- **Power User mock exam:** 65 timed questions drawn from a bank of 129, mapped to the Splunk Core Certified Power User blueprint, with a per-topic breakdown.
- **Field Manual:** a library of corrected, ready-to-use SOC queries.
- **Glossary:** every term explained in plain language.

## How it teaches

1. **Watch me:** a narrated demo types the search one pipe at a time and animates what each command does to the events.
2. **Your turn:** you build the same kind of search yourself.
3. **Quiz:** Kahoot-style rounds, with no question on anything not taught first.

The built-in SPL engine follows real Splunk behaviour: newest-first results, case rules for fields vs values, `NOT` vs `!=` on missing fields, `count(eval())` needing `AS`, and more. What you practise is what you'll see at work.

## Running it

**Online:** open the link above on any phone or computer. Tap once to start the narration. Progress is saved in your browser.

**Offline or on an internal network:** download this repository as a ZIP (*Code → Download ZIP*) and unzip it. Then either:

- double-click `index.html` to run it straight from the folder in Edge or Chrome, or
- serve the folder from any static web server (IIS, nginx, Apache, or `python3 -m http.server`).

The app makes no requests outside its own folder: no fonts, CDNs, analytics or update checks. See `README.txt` for server setup and MIME types.

## Data and privacy

- All logs are **made-up sample data** in the style of the public Splunk BOTS datasets. No real organisation's data is included.
- No accounts, no tracking, no analytics. Progress stays in your own browser.

## Notes

- This is an independent learning project. It is **not affiliated with or endorsed by Splunk Inc.** Splunk, SPL and related names are trademarks of their owners.
- Narration was generated with the open-source Kokoro text-to-speech model.

## License

Free to use for learning.
