# Project 1 - Card Counting Black Jack: Phase 1

## 📋 Description

In this project, you will try to find an optimal Black Jack policy that also attempts to use card counting to beat the dealer in a single-player game (your agent vs. the dealer).

---

## 🃏 Basic Blackjack Setup

The game rules are:

- A standard 52-card deck is used (cards 1–10, J, Q, K across four suits).
- You and the dealer are both dealt two cards:
  - One of the dealer's cards is hidden.
- You can choose to:
  - **STAY** with your current hand
  - **DRAW** another card (repeatable until bust, win, or stay)

### Game Outcomes

- If your sum exceeds 21 → **Lose (-1)**
- If your sum equals 21 → **Win (+1)**
- If you choose to stay < 21, the dealer:
  - Reveals their hidden card
  - Wins if sum = 21
  - Draws if sum ≤ 16
  - Stays if 17 ≤ sum ≤ 20
  - If dealer busts (>21) → **You win**
  - Higher sum wins; tie = **Draw (0)**

### Special Rule

- Aces can count as **1 or 11**, whichever is more beneficial.

> 💡 No card splitting or betting mechanics are implemented.

---

## 🧪 Task 0 – Basic Game Setup

- Implement a basic interactive or visual Blackjack game environment.
- Allow either a human or an RL agent to play against the dealer.
- Visualization can be via simple print statements or a basic GUI.

---

## 🤖 Task 1 – Tabular Q-Learning Agent

Train an agent using tabular Q-learning to learn the optimal policy for:
- When to **STAY**
- When to **DRAW**

### 🔍 Subtasks

#### 1.1: Play a few games against the dealer

- Evaluate the **win percentage** achieved by your trained agent.

#### 1.2: Prove the optimal policy

- If your agent has found an optimal policy, show evidence.
- Report the **expected best win %**:
  - If **< 50%**, you’ll lose money on average.
  - If **> 50%**, you’re **beating the casino**.

---

## 🧠 Task 2 – Card Counting Agent (Hi-Lo)

Now improve your agent’s win rate using basic card counting with the Hi-Lo system.

### 🃏 Hi-Lo Count Rules

- Cards **2–6** → +1
- Cards **7–9** → 0
- Cards **10–Ace** → -1

### Mechanics

- Use a **single deck** of 52 cards.
- Discarded cards remain out until:
  - Fewer than 10 cards remain → reshuffle deck.

### 🔢 Count State Categories

Use the running count as an extra state feature:
- **High**: Count > +5
- **Neutral**: -5 ≤ Count ≤ +5
- **Low**: Count < -5

Train a new tabular Q-learning agent with this extra state dimension.

### ❓ Questions to Answer

- Does the card-counting agent perform better than the Task 1 agent?
- What is the **best average win %** with the new agent?
  - If **> 50%**, you can consistently beat the casino!

---

## 📌 Remarks

- You may optionally explore:
  - Monte Carlo control
  - Policy Iteration / Value Iteration
- If using PI/VI:
  - Calculate transition probabilities (easier than expected, consider Markov Chains)
- Thresholds **(+5, -5)** may be rare in one-deck scenarios—consider experimenting with tighter thresholds.

---

## 🔗 References

- [How to Play Blackjack – Bicycle Cards](https://bicyclecards.com/how-to-play/blackjack)

---

> 🧠 Good luck exploring the math and strategy behind Blackjack!
