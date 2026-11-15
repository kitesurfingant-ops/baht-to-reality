# Ant & Jules' Baht to Reality

A private shared expense and income log for Ant and Jules in Thailand, installed on the iPhone home screen and synced through Supabase (project `ant-data`).

- `index.html` – the whole app
- `config.js` – Supabase URL and publishable key (public by design)
- `icon-*.png` – home screen icon

Data lives in the tables `fin_entries`, `fin_categories`, `fin_fixed` and `fin_households`, with the summary view `fin_monthly_summary`. The tables are closed to the web; the app can only call `fin_config`, `fin_list`, `fin_put`, `fin_del`, `fin_apply_fixed` and `fin_save_config`, which need the household key from each person's private link.

Private link: `https://kitesurfingant-ops.github.io/baht-to-reality/#<ant|jules>.<key>` (the key is not stored in this repo).


## Updating
Bump `APP_VERSION` near the top of the script in `index.html` with every change. When the app opens, it fetches the live page fresh, and if the version differs it reloads onto the new one, so neither phone is stuck on a cached copy.
