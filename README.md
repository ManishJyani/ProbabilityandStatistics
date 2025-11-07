# ProbabilityandStatistics

- Probabilty: Event/(Sample space) - it is very important to think about complete output to get the sample space like throwing dice has sample space of 6 ,tossing coin one time is 2 ans so on. (Event: the possible output user in interested in.)  
- Complement of Probability : P(event)= 1- P(not event)  
- Sum of probability : Disjoint event : simply add them , joint : subtract the common one time .   
- Independent: Occuring of one event doesn't affect the second like what comes in first time in tossing coin does not affect the second so happening these consecutive event we can write in product rule which simplify our calcualation and we don't need to construct the whole sample space . Product rule of independent event : **P(A and B)= P(A)*P(B)**  
- Conditional Probability: Probability of happening one event if second event has already occured.  

                                     **P(A/B)= P(A and B)/P(B)**      
                                     
- Bayes’ Theorem

    **Definition:**  
    Bayes’ theorem is a way to **update our belief** (probability) about something when we get **new evidence**.  
    It connects what we already believe (the **prior**) with how likely the evidence is if our belief were true (the **likelihood**) to give us a new belief (the **posterior**).

    ### 🔢 Formula

    $$P(H | E) = \frac{P(E | H) \times P(H)}{P(E)}$$

    Where:
    - **P(H)** → Prior (initial belief about hypothesis H)  
    - **P(E|H)** → Likelihood (chance of seeing evidence E if H is true)  
    - **P(H|E)** → Posterior (updated belief after seeing E)  

    ---

    ### 🧬 Famous Disease Example

    Suppose:
    - 1% of people have a disease  
    - The test is 99% accurate (true positive and true negative)

    You test positive — what’s the chance you actually have the disease?

$$[
    \begin{align*}
    P(Disease) &= 0.01 \\
    P(Positive|Disease) &= 0.99 \\
    P(Positive|No\,Disease) &= 0.01 
    \end{align*}
]$$

$$[\
    P(Disease|Positive) = \frac{0.99 \times 0.01}{(0.99 \times 0.01) + (0.01 \times 0.99)} \approx 0.50
\]$$

So even with a positive test, there’s only about a **50% chance** you actually have the disease — because the disease is rare.

    ---

## Key Idea
    Bayes’ theorem helps you **update your belief** from a **prior** to a **posterior** when **new evidence** appears.  
    These is used in classification in ML like if what is the probability of a mail to be spam if lottery is in it.
# Naive Bays model
-   When predicting a class (like “spam” or “not spam”), Naïve Bayes assumes that each feature (like the words in an email) contributes to the outcome **independently**, even though in reality, features often influence each other.  
    $$\[
    P(C \mid x_1, x_2, \ldots, x_n) = \frac{P(C) \prod_{i=1}^{n} P(x_i \mid C)}{P(x_1, x_2, \ldots, x_n)}
    \]$$
# 📘 Lecture Summary: Mean & Expected Value

## 1. Concept of the Mean
- The **mean** represents the **center or balance point** of a distribution.  
- It is the value where the data (or probabilities) would balance on a scale.  
- Can be viewed as a **weighted average** of values.  

---

## 2. Sample Mean vs. Expected Value

### 🧩 **Sample Mean** ($\bar{x}$)
- Based on **observed data**.  
- Formula:  
  $$\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i$$  
- Example: Kids’ ages → $\bar{x} = 1.3$ years.  
- Describes the **empirical** or **observed** average from data.

### 🎯 **Expected Value** ($E[X]$)
- Based on a **probability model** or theoretical distribution.  
- Formula (discrete):  
  $$E[X] = \sum_x x \, P(x)$$  
- Formula (continuous):  
  $$E[X] = \int_{-\infty}^{\infty} x \, f(x) \, dx$$  
- Example: Fair coin game → $E[X] = 0.5(10) + 0.5(0) = 5$.  
- Describes the **theoretical mean** or **long-run average**.

**Link:** The *sample mean* is an **estimate** of the *expected value*.  
They share the same formula structure, but:
- $\bar{x}$ uses **observed frequencies**,  
- $E[X]$ uses **true probabilities**.

---

## 3. Key Ideas
- **Mean = balancing point = weighted average.**  
- **Uniform distribution** $[a, b]$:  
  $$E[X] = \frac{a + b}{2}$$  
- **Mean ≠ Median:** the mean shifts toward the tail in skewed data.  
- **Discrete →** summation form; **Continuous →** integral form.  

---

## 📝 Summary
- **Sample Mean ($\bar{x}$):** empirical average from data.  
- **Expected Value ($E[X]$):** theoretical average from probability.  
- Both describe the **center of a distribution** — one from **data**, one from **theory**.


## 📊 Measures of Central Tendency

- **Mean ($\mu$):** Arithmetic average. Sensitive to outliers.  
  $$\mu = \frac{1}{n}\sum_{i=1}^{n} x_i$$

- **Median:** Middle value when data are ordered. Robust to outliers.  

- **Mode:** Most frequent value (highest probability density).  

---

### ⚖️ Skewness and Relationships

$$
\begin{cases}
\text{Symmetric: } \text{Mean} = \text{Median} = \text{Mode} \\
\text{Right-skewed: } \text{Mean} > \text{Median} > \text{Mode} \\
\text{Left-skewed: } \text{Mean} < \text{Median} < \text{Mode}
\end{cases}
$$

---

### 🎯 Examples

**Binomial Distribution ($n=5, p=0.5$):**  
$$\text{Mean} = np = 2.5, \quad \text{Median} = 2.5, \quad \text{Mode} = 2,3$$  

**Normal Distribution:**  
$$\text{Mean} = \text{Median} = \text{Mode}$$


## 🎲 Expected Value of a Function

### 🔹 Definition
For a discrete random variable $X$ with outcomes $x_i$ and probabilities $p(x_i)$:

$$
E[X] = \sum_i x_i \, p(x_i)
$$

For any function $g(X)$:

$$
E[g(X)] = \sum_i g(x_i) \, p(x_i)
$$

---

### 🎯 Example: Dice Game
- Roll a fair die with $p(x_i) = \frac{1}{6}$  
- Payoff = square of the number rolled  

$$
E[X^2] = \sum_{i=1}^{6} i^2 \cdot \frac{1}{6} = \frac{91}{6}
$$

---

### 💰 Linear Transformation of Expectation
If $Y = aX + b$, then:

$$
E[Y] = aE[X] + b
$$

**Implications:**
- $E[aX] = aE[X]$
- $E[b] = b$
- Expectation is a **linear operator**

---

### 🧠 Key Takeaway
Expectation preserves linearity:

$$
E[aX + b] = aE[X] + b
$$

and extends naturally to functions $g(X)$ by replacing $X$ with $g(X)$ in the summation.

## 🎯 Linearity of Expectation

### 🔹 Example 1: Coin + Dice Game
You play two games:
1. **Flip a coin** – win \$1 if heads, \$0 if tails.  
   → Expected value: $E[X_{\text{coin}}] = 0.5$
2. **Roll a die** – win the number rolled.  
   → Expected value: $E[X_{\text{dice}}] = 3.5$

Total winnings:  
$$
E[X_{\text{total}}] = E[X_{\text{coin}}] + E[X_{\text{dice}}] = 0.5 + 3.5 = 4
$$

Hence,  
> **$E[X + Y] = E[X] + E[Y]$**

---

### 🔹 Example 2: Name-Matching Game (Derangement Problem)
- There are $n$ people and $n$ unique names in a bag.  
- Each person randomly receives one name.  
- A *match* occurs when someone gets their own name.

#### 🎲 Case for 3 people (Aisha, Beto, Cameron)
All 6 possible name assignments are equally likely.  
Counting correct matches across all permutations gives:
$$
\text{Average matches} = \frac{3 + 1 + 1 + 1 + 0 + 0}{6} = 1
$$
So, on average, **1 person gets their own name**.

---

### 🔹 General Case for n People
Let:
- $M$ = total number of matches  
- $A_i$ = indicator variable (1 if person *i* gets their name, else 0)

Then:
$$
M = A_1 + A_2 + \dots + A_n
$$

Each person has a $1/n$ chance of receiving their own name:
$$
E[A_i] = \frac{1}{n}
$$

By linearity of expectation:
$$
E[M] = E[A_1] + E[A_2] + \dots + E[A_n] = n \cdot \frac{1}{n} = 1
$$

---

### 🧠 Key Takeaways
- **Linearity of expectation:**  
  $$E[X + Y] = E[X] + E[Y]$$  
  Holds **always** — no matter if variables are **independent or not**.
- Powerful tool for simplifying problems like expected matches or combined outcomes.


## 📈 Variance — Measuring the Spread

### 🔹 Why Variance?
The **expected value** tells us the *center* of a distribution,  
but **not how spread out** the data is.

Two games may have the same mean but very different risks:

- **Game 1:** Win \$1 for heads, lose \$1 for tails  
- **Game 2:** Win \$100 for heads, lose \$100 for tails  

Both have $E[X] = 0$, yet Game 2 is clearly *riskier*.  
This difference in “spread” is captured by **variance**.

---

### 🔹 Building Intuition
Variance measures how far outcomes typically are from the mean.

1. **Deviation:** $x - E[X]$  
   - Average deviation → always 0 (positives and negatives cancel out)  
2. **Absolute deviation:** $|x - E[X]|$  
   - Works conceptually, but difficult to handle mathematically  
3. **Squared deviation:** $(x - E[X])^2$  
   - Always positive and mathematically smooth ✅  

Hence, **variance** is simply the **average squared deviation**:

$$
\text{Var}(X) = E[(X - E[X])^2]
$$

---

### 🔹 Step-by-Step Meaning
1. Find the mean $E[X]$.  
2. Subtract it from each value (deviation).  
3. Square the deviations.  
4. Take the average (weighted by probabilities).  

That’s your variance — a measure of *spread* around the mean.

---

### 🎯 Example
- **Game 1:** Win/Lose \$2 → Variance = 4  
- **Game 2:** Win \$3 or Lose \$1 → Variance = 4  

Even though Game 2 has a higher mean, both have **the same variance**  
because their outcomes are equally spread around their own centers.

---

### 🔹 Alternative Formula
Variance can also be computed using:

$$
\text{Var}(X) = E[X^2] - (E[X])^2
$$

This comes from expanding $(X - E[X])^2$ and using linearity of expectation.

---

### 🔹 Effect of Linear Transformations
If $Y = aX + b$, then:

$$
\text{Var}(Y) = a^2 \, \text{Var}(X)
$$

**Interpretation:**
- Adding $b$ shifts the distribution (changes the center) but not the spread.  
- Multiplying by $a$ *scales* all deviations, so variance grows by $a^2$.

---

### 🧠 Intuitive Recap
- **Mean:** Center  
- **Variance:** Spread  
- **Add a constant ($b$):** Shifts, no change in spread  
- **Multiply by constant ($a$):** Stretch/squeeze → variance × $a^2$

Variance quantifies *how much outcomes fluctuate* —  
the mathematical backbone of “risk” and “uncertainty.”


## 📏 Standard Deviation — Practical Measure of Spread

### 🔹 Why Use It
- **Variance** shows spread but in **squared units** (e.g., m², ft²) — not intuitive.  
- **Standard deviation (σ)** = √Variance gives spread in the **same units** as the data.  

$$
\sigma = \sqrt{\text{Var}(X)}
$$

---

### 🔹 Use Case
- Provides an interpretable measure of variability.  
- In a **normal distribution**, it defines how data is spread around the mean:

| Range | Coverage |
|--------|-----------|
| μ ± 1σ | 68% of data |
| μ ± 2σ | 95% of data |
| μ ± 3σ | 99.7% of data |

---

**In short:**  
Standard deviation is the **real-world measure of uncertainty or consistency** in data — same units, clear meaning, widely used.


# 📈 Adding Gaussian Distributions: A Practical Guide

## 🎯 Core Concept
When you add two independent, normally distributed variables, their sum also follows a Gaussian distribution. This is powerful for modeling real-world systems like computer response times.

## 🔍 Understanding the Building Blocks

### What is a Gaussian Distribution?
Imagine a perfect bell curve - that's a Gaussian distribution. It describes how values cluster around an average.

  ^ Probability
  |
  |           •
  |         • • •
  |       •   •   •
  |     •     •     •
  |   •       •       •
  +---σ---μ---σ---→ Values


**Real-world examples:**
- Processing Time: Typically ~10ms, usually between 6-14ms
- Network Latency: Typically ~5ms, usually between 3-7ms

### What Does "Independent" Mean?
Two variables are independent when one doesn't affect the other. Think of it like:

✅ **Independent Examples:**
- Time to boil water 🍵 + Time to toast bread 🍞
- Your commute time 🚗 + Your friend's commute time 🚴

❌ **Dependent Examples:**
- Time to boil water 🍵 + Time to cook pasta 🍝
- Your commute time 🚗 + Traffic congestion 🚦

## 🧮 The Magic Formula

### Our Scenario:
- **Processing Time (T):** ~10ms ± 2ms
- **Network Latency (L):** ~5ms ± 1ms  
- **Total Response Time (R):** R = T + L

### The Result:

### How We Calculate It:

**Mean (Center Point):**

**Spread (Uncertainty):**

## 📊 Visualizing the Result

  ^
  |           •           | = Processing (10±2ms)
  |         • • •         | = Latency (5±1ms)
  |       •   •   •       | = Total (15±2.24ms)
  |     •     •     •
  |   •       •       •
  +---------|-------|-----→ Time (ms)
           10      15
          (Fast)  (Average)


## 💡 Key Takeaways

1. **The center moves:** 10ms + 5ms = 15ms average response time
2. **The spread grows:** But not simply 2ms + 1ms = 3ms! Instead, we get ~2.24ms
3. **The shape stays Gaussian:** The sum keeps the nice bell curve shape

## 🎯 Practical Interpretation
- **Most common scenario:** ~15ms total response time
- **Typical range:** 15ms ± 2.24ms (about 12.76ms to 17.24ms)
- **Rare cases:** <10.5ms or >19.5ms (very unusual)

This explains why your computer's total response time feels predictable, even though individual components have variability!



