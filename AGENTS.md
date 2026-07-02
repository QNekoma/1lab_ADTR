# AGENTS.md

## Cursor Cloud specific instructions

### Nature of this repository
This repository is **documentation-only coursework** (in Russian), not a runnable
application. It contains Markdown describing a time-series analysis lab and exam
notes:
- `README.md` — Лабораторная работа №1: time-series analysis & forecasting
  (statistical analysis, AR, MA, ARMA/ARIMA).
- The `nolow/exam-tickets-timeseries-4680` branch additionally contains
  `exam_tickets_time_series.md`.

There is **no application, no services, no tests, no build, and no lint config**.
There is nothing to start (no server, database, cache, or ports).

### Development environment
The `README.md` prescribes implementing the lab in Python. The environment set up
here is a Python 3.12 data-science stack installed into system Python via `pip`:
`pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels` (pulls in `scipy`, etc.).
The update script (run automatically on VM startup) reinstalls these.

- No PEP 668 / externally-managed restriction on this image, so plain
  `pip3 install ...` works (no `--break-system-packages` needed).
- Use a non-interactive matplotlib backend when generating plots headlessly:
  `matplotlib.use("Agg")`.

### Verifying the environment
Any script using the recommended libraries confirms readiness. A quick smoke check:

```bash
python3 -c "import pandas, numpy, matplotlib, seaborn, statsmodels; print('ok')"
```

The full lab pipeline (statistical summary, ADF stationarity test, `AutoReg` AR
model, rolling-mean MA smoothing, and `ARIMA` forecasting + a headless matplotlib
plot) runs successfully with this stack.
