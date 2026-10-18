# ♟️ Self-Adaptive Chess Engine & Elo Arena

An interactive, self-contained chess engine that starts from basic legal rules and self-adapts its heuristics, tactical search depth, and evaluation weights. Features a live FIDE Elo rating system and a factory reset option.

## 📁 Package Contents
- `index.html` - Full playable web app with tournament board, 2D Staunton pieces, live Elo chart, AI brain telemetry, and sound effects.
- `chess_adaptive_sim.py` - Headless Python genetic evolution & batch self-play script.
- `README.md` - Documentation and architecture guide.

## 🚀 How to Run
- **Interactive UI**: Double-click `index.html` in Chrome, Edge, or Firefox.
- **Python Simulator**: Run `python chess_adaptive_sim.py` in your terminal.

## 🧠 Self-Adaptive Growth Stages
- **Gen 0: Infant** - Baseline random legal moves, naive captures. Elo ~400-500.
- **Gen 1: Materialist** - Learns standard piece valuation (P=100, N=320, B=330, R=500, Q=900, K=20000). Elo ~800.
- **Gen 2: Positional Strategist** - Integrates Piece-Square Tables (PST), center dominance, and pawn advancement. Elo ~1200.
- **Gen 3+: Master Tactician** - Minimax search with Alpha-Beta pruning, mobility scoring, and dynamic weight tuning. Elo ~1800+.

## 📈 Ranking System (Elo)
- Standard FIDE logistic formula:
  $$E_A = \frac{1}{1 + 10^{(R_B - R_A)/400}}$$
  $$\Delta R_A = K \cdot (S_A - E_A)$$
- Dynamic K-factor ($K=32$) with live HTML5 Canvas graph tracking both player and AI ratings over match history.

## 🔄 Restart / New Start Option
- **New Game**: Clears the board for a new round while preserving accumulated ratings and AI brain weights.
- **Factory Reset (New Start)**: Wipes all evolutionary memory, restores the AI to Generation 0 (Infant, Elo 500), resets player Elo to 1000, and clears the timeline.
