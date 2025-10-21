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


