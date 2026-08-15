# Experiment-02: Simplification of Boolean Expressions Using Boolean Algebra
### Introduction

Boolean algebra provides a simple way to represent and manipulate the logic used in digital circuits. It is based on binary values, where the variables can only be **0 (LOW)** or **1 (HIGH)**.

By applying Boolean rules and theorems, complicated logic expressions can be reduced into simpler equivalent forms. This process is important in digital circuit design because a simplified expression generally requires fewer logic gates, less hardware, and lower implementation cost.

In this experiment, the given Boolean functions are analyzed and simplified step-by-step using the appropriate laws and identities of Boolean algebra.


### Apparatus Required
<ul>
<li>Digital Logic Training Board</li>
<li>Jumper/Connecting Wires</li>
<li>Basic Logic Gate Modules</li>
<li>5 V DC Regulated Power Source</li>
<li>LED Display Indicators</li>
<li>Digital Logic ICs</li>
</ul>

### Procedure
<ol>
  <li>The Boolean functions provided for the experiment were examined and written in their original form.</li>
<li>The variables and logical operations involved in each function were identified.</li>
<li>Suitable Boolean theorems and identities were selected for the simplification process.</li>
<li>The expressions were reduced sequentially by applying the selected laws at each step.</li>
<li>Common, repeated, and unnecessary terms were removed wherever possible.</li>
<li>The resulting expressions were checked to ensure that they were logically equivalent to the original functions.</li>
<li>The simplified functions were considered for practical implementation using logic gates and may be verified with a digital logic trainer.</li>
</ol>

### Calculations:
## Problem-1

Given,

$$
F(A,B,C)=A'BC+AB'C+ABC'+ABC
$$ 

#### 1st Procedure: Using Boolean Expression

Given,

$$
F(A,B,C)=A'BC+AB'C+ABC'+ABC
$$

Add the redundant $ABC$ term where convenient:

$$
F=A'BC+ABC+AB'C+ABC+ABC'+ABC
$$

Grouping the terms:

$$
F=BC(A'+A)+AC(B'+B)+AB(C'+C)
$$

Using,

$$
A'+A=1,\qquad B'+B=1,\qquad C'+C=1
$$

Therefore,

$$
F=BC+AC+AB
$$

Hence,

$$
\boxed{F=AB+AC+BC}
$$

#### Final Answer:

$$
\boxed{F=AB+AC+BC}
$$

<br>

#### 2nd Procedure: K-Map Simplification <br>

Given,

$$
F(A,B,C)=A'BC+AB'C+ABC'+ABC
$$

#### Step 1: Identify the minterms

From the given expression:

$$
A'BC = m_3
$$

$$
AB'C = m_5
$$

$$
ABC' = m_6
$$

$$
ABC = m_7
$$

Therefore,

$$
F(A,B,C)=\Sigma m(3,5,6,7)
$$

#### Step 2: Draw the 3-variable K-Map

Using Gray Code order:

| $AB \backslash C$ | $0$ | $1$ |
|:---:|:---:|:---:|
| $00$ | 0 | 0 |
| $01$ | 0 | **1** |
| $11$ | **1** | **1** |
| $10$ | 0 | **1** |

The 1's are at:

$$
m_3,\ m_5,\ m_6,\ m_7
$$

#### Step 3: Make the groups

#### Group 1: $m_3$ and $m_7$

Common variables:

- $B=1$
- $C=1$
- $A$ changes

Therefore,

$$
m_3+m_7=BC
$$

#### Group 2: $m_5$ and $m_7$

Common variables:

- $A=1$
- $C=1$
- $B$ changes

Therefore,

$$
m_5+m_7=AC
$$

#### Group 3: $m_6$ and $m_7$

Common variables:

- $A=1$
- $B=1$
- $C$ changes

Therefore,

$$
m_6+m_7=AB
$$

#### Step 4: Write the simplified expression

Combining all the groups:

$$
F=BC+AC+AB
$$

Therefore, the final simplified answer is:

$$
\boxed{F(A,B,C)=AB+AC+BC}
$$

#### Before Simplification: 
<img width="623" height="360" alt="image" src="https://github.com/user-attachments/assets/0c5d5bc6-fa5f-453a-be2e-2c0e7d044995" />

#### After Simplification:
<img width="560" height="324" alt="image" src="https://github.com/user-attachments/assets/d5e22ada-6318-4e96-8dff-31f87fd3dd41" />

## Problem 2

Given,

$$
F(A,B,C)=A(A+B)(A+B+C)
$$

#### 1st Procedure: using boolean expression
Using the absorption law,

$$
A(A+B)=A
$$

Therefore,

$$
F=A(A+B+C)
$$

Again, using the absorption law,

$$
A(A+B+C)=A
$$

Therefore,

$$
F=A
$$

### Final Answer:

$$
\boxed{F=A}
$$

#### 2nd Procedure: using K-Map:

#### Step 1: Find the minterms

First, simplify the given expression to determine the truth table values:

$$
F=A(A+B)(A+B+C)
$$

Since $A=1$ is required for the function to be $1$,

$$
F=1 \quad \text{when } A=1
$$

Therefore, the function is $1$ for:

$$
A,B,C = 100,\ 101,\ 110,\ 111
$$

Hence,

$$
F(A,B,C)=\Sigma m(4,5,6,7)
$$

#### Step 2: Draw the 3-variable K-Map

Using Gray Code order:

| $AB \backslash C$ | $0$ | $1$ |
|:---:|:---:|:---:|
| $00$ | 0 | 0 |
| $01$ | 0 | 0 |
| $11$ | **1** | **1** |
| $10$ | **1** | **1** |

#### Step 3: Make the Group

We can group all four 1's together:

$$
m_4,\ m_5,\ m_6,\ m_7
$$

In this group:

- $A=1$ remains constant.
- $B$ changes from $0$ to $1$.
- $C$ changes from $0$ to $1$.

Therefore, the common variable is:

$$
A
$$

#### Step 4: Write the Simplified Expression

Thus,

$$
F=A
$$

#### Final Answer:

$$
\boxed{F=A}
$$

#### Before Simplification:
<img width="584" height="247" alt="image" src="https://github.com/user-attachments/assets/adf3778d-b56c-457d-8820-c8aed29f9be5" />

#### After Simplification:
<img width="406" height="159" alt="image" src="https://github.com/user-attachments/assets/c9132d0f-c86f-42c2-afcc-07eb41701bdf" />

## Problem 3

Given,

$$
F(A,B,C)=(A+(BC)')'(AB+ABC)
$$

#### 1st Procedure: using boolean expression

First, consider the first part:

$$
(A+(BC)')'
$$

Using De Morgan's theorem,

$$
(A+(BC)')'=A'\cdot((BC)')'
$$

Since,

$$
((BC)')'=BC
$$

Therefore,

$$
(A+(BC)')'=A'BC
$$

Now consider the second part:

$$
AB+ABC
$$

Using the absorption law,

$$
AB+ABC=AB
$$

Therefore,

$$
F=A'BC\cdot AB
$$

Since the expression contains both $A'$ and $A$,

$$
A'A=0
$$

Therefore,

$$
F=0
$$

#### using K-Map

Since $F=0$ for all possible combinations of $A$, $B$, and $C$, there are no minterms.

$$
F(A,B,C)=\Sigma m(\varnothing)
$$

The K-Map contains all 0s:

| $AB \backslash C$ | $0$ | $1$ |
|:---:|:---:|:---:|
| $00$ | 0 | 0 |
| $01$ | 0 | 0 |
| $11$ | 0 | 0 |
| $10$ | 0 | 0 |

#### Step 3: K-Map Simplification

There are no 1s to group.

Therefore,

$$
F=0
$$

#### Final Answer:

$$
\boxed{F=0}
$$

#### Before Simplification
<img width="660" height="329" alt="image" src="https://github.com/user-attachments/assets/867e4ee8-896f-4aa6-9555-6f31ab1f6794" />

#### After Simplification
<img width="358" height="233" alt="image" src="https://github.com/user-attachments/assets/2a7b98da-415b-4925-8b61-57ba142bd1ec" />

## Problem 4

Given,

$$
F(A,B,C)=\left[B'(A+B)+(A+B)(A+B')\right]B'
$$

### 1st Procedure: using boolean expression

First, simplify the expression to identify the minterms.

Consider,

$$
B'(A+B)=AB'+B'B
$$

Since,

$$
B'B=0
$$

Therefore,

$$
B'(A+B)=AB'
$$

Now,

$$
(A+B)(A+B')=A
$$

Therefore,

$$
F=(AB'+A)B'
$$

Using the absorption law,

$$
A+AB'=A
$$

Therefore,

$$
F=AB'
$$

Since $C$ does not appear in the simplified expression, the function is $1$ for both values of $C$ when $A=1$ and $B=0$.

Thus,

$$
F(A,B,C)=\Sigma m(4,5)
$$

### 2nd Procedure: using K-Map

Using Gray Code order:

| $AB \backslash C$ | $0$ | $1$ |
|:---:|:---:|:---:|
| $00$ | 0 | 0 |
| $01$ | 0 | 0 |
| $11$ | 0 | 0 |
| $10$ | **1** | **1** |

### Step 3: Make the Group

Group the two adjacent 1's:

$$
m_4,\ m_5
$$

In this group:

- $A=1$ remains constant.
- $B=0$ remains constant.
- $C$ changes.

Therefore, $C$ is eliminated.

The resulting term is:

$$
AB'
$$

### Step 4: Write the Simplified Expression

Therefore,

$$
F=AB'
$$

### Final Answer:

$$
\boxed{F=AB'}
$$

#### Before Simplification
<img width="759" height="360" alt="image" src="https://github.com/user-attachments/assets/5e165baa-f37f-4822-ba93-b64e71e668aa" />

#### After Simplification
<img width="428" height="163" alt="image" src="https://github.com/user-attachments/assets/67fdf0f5-ae75-46e6-8e6f-645233a12f49" />




