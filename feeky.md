# Solana Watchdog Agent – Agent Logic

## Agent Goal
Continuously monitor Solana RPC health and network reliability,
detect anomalies early, and notify humans with contextual explanations
instead of raw metrics.

## Observed Signals
- RPC latency (response time)
- Error rate / timeout frequency
- Slot progression delays
- RPC availability

## Agent Reasoning Flow
1. Collect metrics periodically
2. Compare against rolling baselines
3. Classify severity:
   - Normal
   - Degraded
   - Critical
4. Generate human-readable explanation
5. Decide whether alerting is required

## Autonomous Behavior
- No dashboards required
- No manual thresholds tuning
- Focused on decision-making, not visualization

## Why Agent-based?
Traditional monitoring shows *what* is wrong.
This agent explains *why it matters* and *what to do next*.
## How to Run

```bash
npm install
pm2 start index.js --name solana-watchdog
pm2 save
