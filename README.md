# ⚡ Trading Operating System (Trading OS)
### Phase 1: Real-Time Decision Support, Compliance Matrix & Portfolio Journaling

An enterprise-grade Python trading companion infrastructure engineered to monitor market structural health, calculate algorithmic setup grading, and enforce a strict psychological and financial risk constitution. Built for professional prop traders and asset management compliance tracking.

---

## Architecture Overview

The system is decoupled into modular layers to isolate data ingestion, mathematical rules, state preservation, and user presentation elements:

```text
trading-operating-system/
├── .streamlit/
│   └── config.toml           # Streamlit absolute path mapping rules
├── config/
│   └── trading_rules.json    # Proprietary risk and drawdown configuration constants
├── src/
│   ├── database/
│   │   ├── __init__.py
│   │   ├── models.py         # SQLite schema initializations
│   │   └── storage.py        # Persistence layer for trade logs & EOD reviews
│   ├── engine/
│   │   ├── __init__.py
│   │   └── scorer.py         # SMC evaluation matrices & risk rule checking gates
│   └── dashboard/
│       └── app.py            # Streamlit multi-column real-time portfolio UI
└── README.md                 # System operations manual
```

---

## Deep Dive: Core Component Modules

1. Risk Framework & Scorer (src/engine/scorer.py)

Acts as a multi-criteria filter gatekeeper. Setups are processed dynamically across a 7-point confirmation matrix derived from Smart Money Concepts (SMC) criteria:

- Structural Context (Max 4 pts): High-Timeframe Bias Alignment, Liquidity Sweep Verification, Break of Structure (BOS), and Fair Value Gap (FVG) detection.

- Execution Validation (Max 3 pts): Candlestick rejection behavior, high-volume session alignment (London/NY Killzones), and news macro safety margins.

Grading Tier Scale:

- Score >= 6: Elite Setup (Triggers authorization exceptions and custom risk scaling)

- Score == 5: A+ Setup

- Score == 4: A Setup

- Score < 4: Standard/Denied Setup (Filtered out from direct automated signaling)

2. Persistence Layer (src/database/storage.py & models.py)

Utilizes a native, highly transactional SQLite configuration mapping data into two independent schema environments:

- trades_journal: Tracks live asset behavior, execution prices, session origins, achieved risk-reward ($R:R$) profiles, and technical comments.

- daily_reviews: A mandatory End-of-Day (EOD) behavioral tracking matrix to prevent psychological degradation (FOMO, over-trading, stop-loss tampering).

3. Executive Control UI (src/dashboard/app.py)

A fast-rendering Streamlit interface providing real-time data visibility:

- Live Sidebar Ledger: Monitors absolute drawdown restrictions against the contract boundaries. If the threshold is broken or consecutive losses exceed bounds, a global lock state is visually triggered.

- Dynamic Scanners: Renders current structural signals intercepted across MetaTrader 5 (MT5) backends.

- Asynchronous Log Forms: Allows immediate manual logging and data synchronization to the persistent layer.

## Installation & Local Environment Spinning

1. Prerequisite Initialization

Ensure you have Python 3.10+ installed. Clone this repository and establish your isolated virtual environment:

```bash
python -m venv .venv

.\.venv\Scripts\Activate.ps1
```

---

2. Package Integration

Install the optimized core framework modules required for operation:

```bash
pip install streamlit pandas
```

---

3. Running the Operational Dashboard

To launch the Executive UI without directory routing path errors, initialize it with explicit PYTHONPATH targeting from the project root:

```text
$env:PYTHONPATH="."
streamlit run src/dashboard/app.py
```

---

## System Testing Harness

Each functional module contains an autonomous local verification block (if __name__ == "__main__":). Run them independently inside your terminal to verify framework integrity:

```bash
python src/database/models.py

python src/engine/scorer.py
```

---


## Architecture Design & Engineering

**Lead Engineer:** Prince Boyard MBOUNGOU NGOMA

**Professional Title:** Network Security & Automation Engineer

**Core Specialization:** Technical Infrastructure, Secure Software Architectures & Python Automation Solutions

**Developed under strict technical specifications for secure, robust, and rule-based discretionary portfolio execution.** 