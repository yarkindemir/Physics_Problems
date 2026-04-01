## 12. Work and Energy with a Constant Force

Given:

$$
\vec F = (6,2)\ \text{N}
$$

$$
m = 2\ \text{kg}
$$

Initial velocity:

$$
\vec v(0) = (1,-1)\ \text{m/s}
$$

Initial position:

$$
\vec r(0) = (0,0)\ \text{m}
$$

Find:

- acceleration
- velocity
- position
- trajectory
- work done at $t=3$ s
- check the work-energy theorem

---

### Step 1: Find acceleration

Using Newton’s second law:

$$
\vec a = \frac{\vec F}{m}
$$

$$
\vec a = \left(\frac{6}{2},\frac{2}{2}\right)
$$

$$
\vec a = (3,1)\ \text{m/s}^2
$$

---

### Step 2: Find velocity

Formula:

$$
\vec v(t)=\vec v_0+\vec a t
$$

Substitute:

$$
\vec v(t)=(1,-1)+(3,1)t
$$

$$
\vec v(t)=(1+3t,\ -1+t)
$$

---

### Step 3: Find position

Formula:

$$
\vec r(t)=\vec r_0+\vec v_0 t+\frac{1}{2}\vec a t^2
$$

Substitute:

$$
\vec r(t)=(0,0)+(1,-1)t+\frac{1}{2}(3,1)t^2
$$

$$
\vec r(t)=\left(t+\frac{3}{2}t^2,\ -t+\frac{1}{2}t^2\right)
$$

---

### Step 4: Trajectory

The motion is given by:

$$
x=t+\frac{3}{2}t^2
$$

$$
y=-t+\frac{1}{2}t^2
$$

So the path is a **parabola**.

---

### Step 5: Work done at $t=3$ s

First find the position at $t=3$:

$$
x(3)=3+\frac{3}{2}(9)=3+13.5=16.5
$$

$$
y(3)=-3+\frac{1}{2}(9)=-3+4.5=1.5
$$

So:

$$
\vec r(3)=(16.5,1.5)
$$

Work formula:

$$
W=\vec F\cdot \vec r
$$

$$
W=(6,2)\cdot(16.5,1.5)
$$

$$
W=6(16.5)+2(1.5)
$$

$$
W=99+3
$$

$$
W=102\ \text{J}
$$

---

### Step 6: Check the work-energy theorem

Initial kinetic energy:

$$
K_0=\frac{1}{2}mv_0^2
$$

Initial speed squared:

$$
v_0^2=1^2+(-1)^2=2
$$

$$
K_0=\frac{1}{2}(2)(2)=2\ \text{J}
$$

Now find velocity at $t=3$:

$$
\vec v(3)=(1+3\cdot3,\ -1+3)
$$

$$
\vec v(3)=(10,2)
$$

Final speed squared:

$$
v^2=10^2+2^2=100+4=104
$$

Final kinetic energy:

$$
K=\frac{1}{2}(2)(104)=104\ \text{J}
$$

Change in kinetic energy:

$$
\Delta K=104-2=102\ \text{J}
$$

So:

$$
W=\Delta K
$$

The work-energy theorem is correct.

---

## Final Answers

Acceleration:

$$
\boxed{\vec a=(3,1)\ \text{m/s}^2}
$$

Velocity:

$$
\boxed{\vec v(t)=(1+3t,\ -1+t)}
$$

Position:

$$
\boxed{\vec r(t)=\left(t+\frac{3}{2}t^2,\ -t+\frac{1}{2}t^2\right)}
$$

Work at $t=3$:

$$
\boxed{W=102\ \text{J}}
$$

Work-energy theorem:

$$
\boxed{W=\Delta K}
$$