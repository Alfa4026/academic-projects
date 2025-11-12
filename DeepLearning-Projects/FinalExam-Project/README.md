# 🚀 Deep Learning Final Project: RNN vs. LSTM vs. LSTM-Attention

This repository contains the final project for our Deep Learning course.

**By: Group 3**
* ALIF ALAMSYAH (11220940000028)
* IBNULLABIB (11220940000037)

---

## 🎯 The Goal

This project pits three sequence model architectures (RNN, LSTM, and LSTM + Attention) against each other to see which one is the champ at "remembering" a sequence of numbers (digits 0-9) while ignoring "noise" (a blank token, `10`).

The task is simple but tricky:

* **Input:** A sequence of digits (0-9).
* **Noise:** The number `10` (our *blank token*) is inserted into the sequence.
* **Goal:** The model must predict the *original* sequence of digits, as if the noise never existed.

> **Example:**
> * `SAMPLE DATA` (input + noise): `[2, 9, 2, 0, 0, 10, 10, 10]`
> * `TARGET` (expected prediction): `[2, 9, 2, 0, 0]`

We wanted to compare their training/validation loss, analyze their gradients, and see the qualitative results.

---

## 🧪 The Scenarios

We tested the models in two scenarios to see how tough they really are:

1.  **Scenario 1: Structured Noise (Easy Mode)**
    * All noise tokens (`10`) are placed consistently at the **end** of the sequence. The model just needs to learn to copy the first 10 digits.

2.  **Scenario 2: Random Noise (Hard Mode)**
    * Noise tokens are inserted at **random positions** throughout the sequence. The model can no longer rely on position and must actually learn to "remember" the important digits while "ignoring" the noise.

---

## 🤖 The Contenders

We implemented three different architectures to see how they stack up:

1.  **Simple RNN (`RNNmodel`)**
    * A standard RNN. We predicted this one would struggle due to the *vanishing gradient* problem on long sequences.

2.  **Simple LSTM (`LSTMmodel`)**
    * A standard LSTM. We expected this to be much better than the RNN, thanks to its *memory cell* that can retain long-term information.

3.  **LSTM + Attention (`LSTM_Attention_Model`)**
    * The "advanced" model. This is an LSTM upgraded with an *Attention Mechanism*. In theory, this is the most sophisticated. *Attention* allows the model to dynamically "focus" on only the relevant parts of the input (digits 0-9) and "ignore" the noise (digit 10), no matter where it appears.

---

## 📊 Results & Key Findings

Spoiler alert: **Attention is the clear winner!** The experiment showed a drastic performance difference between the three models.

### 1. Training & Validation Loss Comparison

![Grafik Perbandingan Loss](./images/Perbandingan%20Metrik%20Training%20dan%20Validasi.png)

* **RNN (Total Fail ❌):** As expected, the simple RNN hit a **vanishing gradient** wall. Its loss curve (both training and validation) stayed flat at a high level. It learned nothing.
* **LSTM (Pretty Good ✅):** Much better than the RNN. In Scenario 1 (easy), it learned the pattern well. But in Scenario 2 (hard), its training loss became unstable and fluctuated. It got "confused" by the random noise.
* **LSTM + Attention (The Champion 🏆):** This model shined, especially in Scenario 2. The attention mechanism made it incredibly resilient to random noise. It successfully learned to focus only on the 0-9 digits and ignore the 10s. This is proven by its loss curve, which dropped the fastest and most stably in both scenarios.

### 2. Gradient Magnitude Comparison

![Grafik Magnitudo Gradien](./images/Perbandingan%20Magnitudo%20Gradien.png)

This graph confirms *why* the models performed the way they did:

* **RNN** shows its gradient dropping straight to zero (*vanishing gradient*).
* **LSTM** (in Scenario 2) shows unstable and sometimes "exploding" gradients (high spikes), indicating the model was "struggling" to adapt to the random noise.
* **LSTM Attention** (in Scenario 2) interestingly shows a **more stable** gradient than in the *easier* scenario. This proves the attention mechanism was highly effective at filtering the noise, so its learning process remained stable and controlled.

### 3. Qualitative Evaluation (5 Random Samples)

The evaluation on 5 random samples from Scenario 2 (Hard Mode) sealed the deal:

* **RNN:** Very low accuracy (0%-30%). Its predictions were mostly wrong.
* **LSTM:** Much better, achieving 90%-100% accuracy on several samples.
* **LSTM + Attention:** Perfect. It scored **100% accuracy** on all tested samples.

---

## 💡 Conclusion

This experiment really shows why architecture matters in deep learning:

1.  **Standard RNNs** are unsuitable for long, noisy sequences due to the *vanishing gradient* problem.
2.  **LSTMs** are far superior thanks to their *memory cells*, but they can still get "confused" and struggle when noise is random and unpredictable.
3.  **LSTM with Attention** is the most robust architecture for this task. Its ability to "selectively focus" on important information while filtering out junk is a true game-changer for "dirty" or unstructured sequence data.

---

## 🚀 How to Run

1.  Ensure all dependencies below are installed.
2.  Open the `.ipynb` file (Google Colab is recommended).
3.  Select a **GPU runtime** (if available) for faster training.
4.  Run all cells from top to bottom (`Run all`).

## 🛠️ Dependencies

* `torch`
* `pandas`
* `matplotlib`
* `numpy`
