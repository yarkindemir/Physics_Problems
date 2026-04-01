## 11. Dynamics with a Time-Dependent Force

Given:

$$
\vec F = (15t,\ 3t-12,\ -6t^2)\ \text{N}
$$

Mass:

$$
m = 3\ \text{kg}
$$

Initial conditions:

$$
\vec r(0) = (5,2,-3)
$$

$$
\vec v(0) = (2,0,1)
$$

Find:

- velocity as a function of time
- position as a function of time

---

### Step 1: Find acceleration

Using Newton’s second law:

$$
\vec a = \frac{\vec F}{m}
$$

$$
\vec a = \left(\frac{15t}{3},\frac{3t-12}{3},\frac{-6t^2}{3}\right)
$$

$$
\vec a = (5t,\ t-4,\ -2t^2)
$$

---

### Step 2: Find velocity

Velocity is the integral of acceleration.

#### x-component

$$
a_x = 5t
$$

$$
v_x = \int 5t\,dt = \frac{5}{2}t^2 + C_1
$$

Use initial condition:

$$
v_x(0)=2
$$

So:

$$
C_1=2
$$

Therefore:

$$
v_x = 2 + \frac{5}{2}t^2
$$

#### y-component

$$
a_y = t-4
$$

$$
v_y = \int (t-4)\,dt = \frac{1}{2}t^2 - 4t + C_2
$$

Use initial condition:

$$
v_y(0)=0
$$

So:

$$
C_2=0
$$

Therefore:

$$
v_y = \frac{1}{2}t^2 - 4t
$$

#### z-component

$$
a_z = -2t^2
$$

$$
v_z = \int -2t^2\,dt = -\frac{2}{3}t^3 + C_3
$$

Use initial condition:

$$
v_z(0)=1
$$

So:

$$
C_3=1
$$

Therefore:

$$
v_z = 1 - \frac{2}{3}t^3
$$

So the velocity vector is:

$$
\vec v(t) = \left(2+\frac{5}{2}t^2,\ \frac{1}{2}t^2-4t,\ 1-\frac{2}{3}t^3\right)
$$

---

### Step 3: Find position

Position is the integral of velocity.

#### x-component

$$
x(t)=\int \left(2+\frac{5}{2}t^2\right)dt
$$

$$
x(t)=2t+\frac{5}{6}t^3+C_4
$$

Use initial condition:

$$
x(0)=5
$$

So:

$$
C_4=5
$$

Therefore:

$$
x(t)=5+2t+\frac{5}{6}t^3
$$

#### y-component

$$
y(t)=\int \left(\frac{1}{2}t^2-4t\right)dt
$$

$$
y(t)=\frac{1}{6}t^3-2t^2+C_5
$$

Use initial condition:

$$
y(0)=2
$$

So:

$$
C_5=2
$$

Therefore:

$$
y(t)=2+\frac{1}{6}t^3-2t^2
$$

#### z-component

$$
z(t)=\int \left(1-\frac{2}{3}t^3\right)dt
$$

$$
z(t)=t-\frac{1}{6}t^4+C_6
$$

Use initial condition:

$$
z(0)=-3
$$

So:

$$
C_6=-3
$$

Therefore:

$$
z(t)=-3+t-\frac{1}{6}t^4
$$

So the position vector is:

$$
\vec r(t)=\left(5+2t+\frac{5}{6}t^3,\ 2+\frac{1}{6}t^3-2t^2,\ -3+t-\frac{1}{6}t^4\right)
$$

---

## Final Answers

Velocity:

$$
\boxed{
\vec v(t)=\left(2+\frac{5}{2}t^2,\ \frac{1}{2}t^2-4t,\ 1-\frac{2}{3}t^3\right)
}
$$

Position:

$$
\boxed{
\vec r(t)=\left(5+2t+\frac{5}{6}t^3,\ 2+\frac{1}{6}t^3-2t^2,\ -3+t-\frac{1}{6}t^4\right)
}
$$