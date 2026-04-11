# Multi‑Total Waterfall Chart for Power BI (Deneb)

Power BI includes a native Waterfall visual — however it **does not correctly support multiple intermediate totals**.

This repository demonstrates a **custom waterfall chart** built using **Deneb (Vega‑Lite)** that supports **true multiple totals**, matching Excel‑style financial waterfall behavior.


## ❓ Why not use Power BI’s native Waterfall?

Power BI’s default Waterfall visual is designed for **a single running total**:
- One start
- Sequential increases/decreases
- One final total

Real‑world financial and project‑control use cases often need **multiple totals**, such as:
- Budget → Current Budget → Forecast
- Original Commitment → Changes → EAC
- Phase‑based or lifecycle‑based rollups

### Native Waterfall limitations
- ❌ Intermediate totals do **not reset** the running calculation
- ❌ Subsequent steps continue from the original baseline
- ❌ Workarounds require fragile data reshaping or duplicated rows

---

## ✅ What this visual solves

This Deneb waterfall chart:

- ✅ Supports **multiple totals in a single visual**
- ✅ Resets the baseline after each total
- ✅ Uses explicit, transparent calculations
- ✅ Works entirely inside Power BI

Each step marked as a **Total**:
- Anchors at zero
- Becomes the baseline for the next segment
- Starts a new accumulation cleanly

---

## 🧠 How it works (conceptually)

Inside the Vega‑Lite specification, the chart:
- Identifies total rows using a boolean flag
- Creates **segments** that reset after each total
- Accumulates deltas **within each segment**
- Draws totals from zero and deltas between segment endpoints

All behavior is declarative and visible in the spec.

---

## 📦 Repository contents

| Path | Description |
|---|---|
| `WaterFall Chart.pbix` | Power BI report with embedded data and Deneb visual |
| `Water Fall Chart.png` | Screenshot of the rendered chart |
| `data.json` | Deneb / Vega‑Lite spec used to render the multi‑total waterfall |
| `README.md` | Documentation |

---

## 🛠 How to use

1. Download the PBIX file  
2. Open in Power BI Desktop  
3. Select the Deneb visual  
4. Review or reuse the Vega‑Lite specification  
5. Replace the embedded data with your own if needed

---

## 📸 Preview

See `Water Fall Chart.png`

---

# 📜 License

MIT License

Copyright (c) 2026 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

