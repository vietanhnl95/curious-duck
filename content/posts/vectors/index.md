---
title: "Math Test"
date: 2021-09-03T11:31:40+07:00
draft: false
categories: [Linear Algebra]
tags: [math]
author: Curious Duck
math: true
---
### Linear combination:
With a set of vectors {$\vec{v_1}$, $\vec{v_2}$, ..., $\vec{v_n}$} in $\mathbb{R}^n$, the linear combination of those vectors is: $$ c_{1}\vec{v_1} + c_{2}\vec{v_2} + ... + c_{n}\vec{v_n} $$

*Examples*

In $\mathbb{R}^2$, we have 2 vectors: $\vec{v} = (1,2)$ and $\vec{w} = (4,-1)$:
$2\begin{bmatrix}  1 \\ 2 \end{bmatrix}$  + 3$\begin{bmatrix}  4 \\ -1 \end{bmatrix}$
$\begin{bmatrix} a & b \\ c & d \end{bmatrix}$
- $2(1,2) + 3(4,-1)$  is a linear combination of $\vec{v}$ and $\vec{w}$
- $5(1,2) - 1(4,-1)$  is also a linear combination of $\vec{v}$ and $\vec{w}$

---
### Vector operations

With $\vec{v}=(v_1, v_2)$ and $\vec{w}=(w_1, w_2)$ in $\mathbb{R}^2$

- Addition: $$\vec{v} + \vec{w} = (v_1 + w_1, v_2 + w_2)$$
- Scalar Multiplication: $$c\vec{v} = (cv_1, cv_2)$$
- Length of a vector: $$||\vec{v}|| = \sqrt{\vec{v}.\vec{v}} = \sqrt{v_1^2 + v_2^2}$$
- A **unit vector** is vector whose length equal 1:
    - $||\vec{u}|| = 1$
    - $\vec{u} = \frac{\vec{v}}{||\vec{v}||}$ (*a unit vector is equal to a vector divided by its length*)
 - Dot product: $$\vec{v}.\vec{w} = v_1w_1 + v_2w_2$$
 - The dot product reveals the angle between 2 vectors:
$$cos\theta = \frac{\vec{v}}{||\vec{v}||}.\frac{\vec{w}}{||\vec{w}||} = \vec{u_v}.\vec{u_w}$$ with $\vec{u_v}$ and $\vec{u_w}$ are the 2 unit vectors of $\vec{v}$ and $\vec{w}$
