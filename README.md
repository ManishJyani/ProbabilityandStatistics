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

\section*{Measures of Central Tendency}

\begin{itemize}
  \item \textbf{Mean ($\mu$):} Arithmetic average. Sensitive to outliers.
    \[
      \mu = \frac{1}{n}\sum_{i=1}^{n} x_i
    \]
  \item \textbf{Median:} Middle value when data are ordered. Robust to outliers.
  \item \textbf{Mode:} Most frequent value (highest probability density).
\end{itemize}

\subsection*{Skewness and Relationships}
\[
\begin{cases}
\text{Symmetric: } \text{Mean} = \text{Median} = \text{Mode} \\
\text{Right-skewed: } \text{Mean} > \text{Median} > \text{Mode} \\
\text{Left-skewed: } \text{Mean} < \text{Median} < \text{Mode}
\end{cases}
\]

\subsection*{Example (Binomial, $n=5, p=0.5$)}
\[
\text{Mean} = np = 2.5, \quad
\text{Median} = 2.5, \quad
\text{Mode} = 2,3
\]

\subsection*{Example (Normal Distribution)}
\[
\text{Mean} = \text{Median} = \text{Mode}
\]



