## 8. Work of a Variable Force

Given the force:

$$
F(x) = -kx
$$

Find:

- the equation of motion and its solution
- the work done from $0$ to $x_0$
- the potential energy
- check that $F = -\frac{dU}{dx}$

---

### Step 1: Equation of motion

Using Newton’s second law:

$$
F = m\ddot{x}
$$

Since

$$
F(x) = -kx
$$

we get:

$$
m\ddot{x} = -kx
$$

Move everything to one side:

$$
m\ddot{x} + kx = 0
$$

This is the equation of simple harmonic motion.

---

### Step 2: Solution of the equation

The standard solution is:

$$
x(t) = A\cos(\omega t) + B\sin(\omega t)
$$

where

$$
\omega = \sqrt{\frac{k}{m}}
$$

So the motion is oscillatory.

---

### Step 3: Work done from $0$ to $x_0$

Work is:

$$
W = \int_0^{x_0} F(x)\,dx
$$

Substitute $F(x) = -kx$:

$$
W = \int_0^{x_0} -kx\,dx
$$

Take out $-k$:

$$
W = -k \int_0^{x_0} x\,dx
$$

Integrate:

$$
W = -k \left[\frac{x^2}{2}\right]_0^{x_0}
$$

$$
W = -\frac{1}{2}kx_0^2
$$

---

### Step 4: Potential energy

Potential energy is:

$$
U(x) = \frac{1}{2}kx^2
$$

At $x = x_0$:

$$
U(x_0) = \frac{1}{2}kx_0^2
$$

So the work done by the force is negative, and the stored potential energy is positive.

---

### Step 5: Check the relation

We know:

$$
U(x) = \frac{1}{2}kx^2
$$

Differentiate:

$$
\frac{dU}{dx} = kx
$$

Then:

$$
-\frac{dU}{dx} = -kx
$$

Since

$$
F(x) = -kx
$$

we get:

$$
F = -\frac{dU}{dx}
$$

So the relation is correct.

---

## Final Answers

Equation of motion:

$$
\boxed{m\ddot{x} + kx = 0}
$$

Solution:

$$
\boxed{x(t) = A\cos(\omega t) + B\sin(\omega t)}
$$

where

$$
\boxed{\omega = \sqrt{\frac{k}{m}}}
$$

Work from $0$ to $x_0$:

$$
\boxed{W = -\frac{1}{2}kx_0^2}
$$

Potential energy:

$$
\boxed{U(x) = \frac{1}{2}kx^2}
$$

Verification:

$$
\boxed{F = -\frac{dU}{dx}}
$$