# Mini Classroom Climate Agent (AI Fundamentals Final Project)

**Repository:** [https://github.com/erasylbaizen/mini-classroom-climate-agent](https://github.com/erasylbaizen/mini-classroom-climate-agent)

A compact, console-based AI agent that manages classroom temperature by combining three core Artificial Intelligence algorithms: **Hill Climbing**, **Bayesian Inference**, and a **Markov Decision Process (MDP)**.

## Problem Statement
Classroom climate control requires balancing student thermal comfort against unnecessary electricity consumption while dealing with noisy temperature sensors. This agent solves the problem in three connected stages:
1. **Setpoint Optimization (Hill Climbing):** Finds the optimal target temperature from 5 candidate setpoints based on predefined comfort and energy-efficiency scores.
2. **State Estimation (Bayesian Inference):** Updates the probability that the classroom is genuinely `Too Hot` given a noisy sensor reading (`ALERT` or `NORMAL`).
3. **Rational Decision Making (MDP):** Evaluates one-step expected rewards to decide whether to activate cooling (`Cool`) or conserve energy (`Wait`).

---

## Explicit Assumptions
* **Candidate Setpoints:** `[18°C, 20°C, 22°C, 24°C, 26°C]` with utility scores `[45, 72, 95, 80, 50]`.
* **Hidden Classroom States:** `Too Hot` and `Normal` (default prior: `P(Too Hot) = 0.30`).
* **Sensor Noise Model:**
  * `P(ALERT | Too Hot) = 0.85` (true positive rate)
  * `P(ALERT | Normal) = 0.15` (false alarm rate)
* **MDP Model:** 2 states (`Too Hot`, `Normal`), 2 actions (`Cool`, `Wait`), with predefined transition probabilities and one-step rewards balancing thermal comfort (`+10`) against heat discomfort (`-10`) and energy waste (`-2` to `-5`).

---

## Project Structure
* `climate_agent.py` — Main Python script implementing Hill Climbing, Bayesian Inference, MDP decision-making, and an interactive CLI menu with built-in test cases.
* `README.md` — Project overview, setup instructions, assumptions, and sample execution logs.

---

## How to Run
1. Make sure **Python 3.8+** is installed (only the Python standard library is used; no external packages are required).
2. Clone the repository:
   ```bash
   git clone [https://github.com/erasylbaizen/mini-classroom-climate-agent.git](https://github.com/erasylbaizen/mini-classroom-climate-agent.git)
   cd mini-classroom-climate-agent

  Team Members

    Yerassyl Baizen: Algorithm implementation (climate_agent.py), CLI interface,  Documentation (README.md) and GitHub repository setup.

    Ainur Albiyeva: Documentation (README.md & Technical Report), presentation slides and test cases.
