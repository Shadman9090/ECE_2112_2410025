# Experiment-02: Simplification of Boolean Expressions Using Boolean Algebra

### Introduction

Boolean algebra provides a simple way to represent and manipulate the logic used in digital circuits. It is based on binary values, where the variables can only be **0 (LOW)** or **1 (HIGH)**.

By applying Boolean rules and theorems, complicated logic expressions can be reduced into simpler equivalent forms. This process is important in digital circuit design because a simplified expression generally requires fewer logic gates, less hardware, and lower implementation cost.

In this experiment, the given Boolean functions are analyzed and simplified step-by-step using the appropriate laws and identities of Boolean algebra. The simplified expressions are then considered for practical implementation using logic gates.

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
<li>The simplified functions were implemented using appropriate logic gates and the outputs were observed.</li>
</ol>

### Calculations

## Problem-1

Given,

$$
F(A,B,C)=A'BC+AB'C+ABC'+ABC
$$

### 1st Procedure: Using Boolean Expression

Given,

$$
F=A'BC+AB'C+ABC'+ABC
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

### Final Answer:

$$
\boxed{F=AB+AC+BC}
$$

### 2nd Procedure: K-Map Simplification

Given,

$$
F(A,B,C)=A'BC+AB'C+ABC'+ABC
$$

#### Step 1: Identify the minterms

From the given expression:

$$
A'BC=m_3
$$

$$
AB'C=m_5
$$

$$
ABC'=m_6
$$

$$
ABC=m_7
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

**Group 1: $m_3$ and $m_7$**

Common variables:

- $B=1$
- $C=1$
- $A$ changes

Therefore,

$$
m_3+m_7=BC
$$

**Group 2: $m_5$ and $m_7$**

Common variables:

- $A=1$
- $C=1$
- $B$ changes

Therefore,

$$
m_5+m_7=AC
$$

**Group 3: $m_6$ and $m_7$**

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

Therefore,

$$
\boxed{F(A,B,C)=AB+AC+BC}
$$

### Practical Circuit Implementation

<img width="918" height="474" alt="image" src="https://github.com/user-attachments/assets/24987f59-1eeb-4b9b-a0eb-ac7fd0e93964" />


The simplified function was implemented using three 2-input AND gates followed by an OR gate:

$$
F=AB+AC+BC
$$

The circuit uses the three product terms $AB$, $AC$, and $BC$ as inputs to the OR stage.

---

## Problem-2

Given,

$$
F(A,B,C)=A(A+B)(A+B+C)
$$

### 1st Procedure: Using Boolean Expression

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

### 2nd Procedure: K-Map Simplification

#### Step 1: Find the minterms

Since $A=1$ is required for the function to be $1$,

$$
F=1 \quad \text{when } A=1
$$

Therefore, the function is 1 for:

$$
A,B,C=100,\ 101,\ 110,\ 111
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

All four 1's can be grouped together:

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

### Final Answer:

$$
\boxed{F=A}
$$

### Practical Circuit Implementation

<img width="345" height="116" alt="image" src="https://github.com/user-attachments/assets/a559cc99-4769-4fac-8d15-c2ee36343d0d" />


Since the simplified expression is simply $F=A$, the output can be obtained directly from input $A$. No AND or OR gate is required for the simplified implementation.

---

## Problem-3

Given,

$$
F(A,B,C)=(A+(BC)')'(AB+ABC)
$$

### 1st Procedure: Using Boolean Expression

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

### Final Answer:

$$
\boxed{F=0}
$$

### 2nd Procedure: K-Map Simplification

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

There are no 1's to group.

Therefore,

$$
F=0
$$

### Final Answer:

$$
\boxed{F=0}
$$

### Practical Circuit Implementation

<img width="490" height="240" alt="image" src="https://github.com/user-attachments/assets/54759a9d-b5ea-49ee-9e86-2f5af6c27ca5" />


The simplified output is always LOW:

$$
F=0
$$

Thus, the circuit output remains 0 for every possible combination of the input variables.

---

## Problem-4

Given,

$$
F(A,B,C)=\left[B'(A+B)+(A+B)(A+B')\right]B'
$$

### 1st Procedure: Using Boolean Expression

First, simplify the first term:

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

Since $C$ does not appear in the simplified expression, the function is 1 for both values of $C$ when $A=1$ and $B=0$.

Thus,

$$
F(A,B,C)=\Sigma m(4,5)
$$

### 2nd Procedure: K-Map Simplification

Using Gray Code order:

| $AB \backslash C$ | $0$ | $1$ |
|:---:|:---:|:---:|
| $00$ | 0 | 0 |
| $01$ | 0 | 0 |
| $11$ | 0 | 0 |
| $10$ | **1** | **1** |

#### Step 1: Make the Group

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

#### Step 2: Write the Simplified Expression

Therefore,

$$
F=AB'
$$

### Final Answer:

$$
\boxed{F=AB'}
$$

### Practical Circuit Implementation

The simplified function is:

$$
F=AB'
$$

Therefore, $B$ is first passed through a NOT gate and then combined with $A$ using an AND gate.

---

## Circuit Implementation

<img width="524" height="188" alt="image" src="https://github.com/user-attachments/assets/9f7020d0-826a-4207-ac92-cff30fb2c050" />


The simplified expressions were implemented using basic logic gates. The following diagram shows the practical circuit implementations prepared for the four problems.



### Observed Results

The implemented circuits produced the expected simplified outputs:

| Problem | Simplified Function | Expected Output |
|:---:|:---:|:---:|
| 1 | $AB+AC+BC$ | Correct |
| 2 | $A$ | Correct |
| 3 | $0$ | Always LOW |
| 4 | $AB'$ | Correct |

### Discussion

The Boolean expressions were successfully simplified using Boolean algebra and verified using K-Map techniques. The simplified forms require fewer logic operations than the original expressions, which reduces circuit complexity.

For Problem-1, the original four minterm expression was reduced to three product terms. Problem-2 was reduced directly to $A$ using the absorption law. Problem-3 was reduced to the constant logic value $0$ because the expression contains both $A$ and $A'$. Problem-4 was reduced to $AB'$, requiring only one NOT gate and one AND gate.

The practical gate implementations were consistent with the obtained simplified expressions. Hence, the experiment demonstrates how Boolean algebra and K-Maps can be used to minimize digital logic circuits and reduce the required hardware.

### Conclusion

The given Boolean expressions were successfully simplified using Boolean algebra and K-Map methods. The simplified expressions were obtained as:

$$
\boxed{F_1=AB+AC+BC}
$$

$$
\boxed{F_2=A}
$$

$$
\boxed{F_3=0}
$$

$$
\boxed{F_4=AB'}
$$

The corresponding logic circuits were implemented using basic gates, and the observed outputs agreed with the expected results. This experiment demonstrates the importance of Boolean simplification in designing simpler, more efficient, and economical digital logic circuits.
