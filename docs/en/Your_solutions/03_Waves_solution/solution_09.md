<h2>9. Damped Oscillator</h2>

<p><strong>Given equation:</strong></p>
<p>m(d²x/dt²) + b(dx/dt) + kx = 0</p>

<p><strong>Goal:</strong></p>
<p>
Study how the damping parameter <strong>b</strong> changes the motion of the system.
We want to describe the three cases:
</p>

<ul>
  <li>Underdamped</li>
  <li>Critically damped</li>
  <li>Overdamped</li>
</ul>

<hr>

<p><strong>1) Write down the general solution</strong></p>

<p>
We start by assuming a solution of the form:
</p>

<p>x(t) = e<sup>rt</sup></p>

<p>
Substitute this into the differential equation:
</p>

<p>m r² e<sup>rt</sup> + b r e<sup>rt</sup> + k e<sup>rt</sup> = 0</p>

<p>
Since e<sup>rt</sup> is never zero, we get the characteristic equation:
</p>

<p>mr² + br + k = 0</p>

<p><strong>Now solve for r:</strong></p>

<p>r = [ -b ± √(b² - 4mk) ] / 2m</p>

<p>
The type of motion depends on the value of the discriminant:
</p>

<p>b² - 4mk</p>

<hr>

<p><strong>2) Classification of cases</strong></p>

<p><strong>a) Underdamped case</strong></p>
<p>
If:
</p>
<p>b² &lt; 4mk</p>

<p>
Then the roots are complex:
</p>

<p>r = -b/2m ± i&omega;<sub>d</sub></p>

<p>
where
</p>

<p>&omega;<sub>d</sub> = √(k/m - b²/4m²)</p>

<p>
So the solution is:
</p>

<p>x(t) = e<sup>-bt/2m</sup> [ C<sub>1</sub> cos(&omega;<sub>d</sub>t) + C<sub>2</sub> sin(&omega;<sub>d</sub>t) ]</p>

<p>
This means the system oscillates, but the amplitude gets smaller with time.
</p>

<p><strong>b) Critically damped case</strong></p>
<p>
If:
</p>
<p>b² = 4mk</p>

<p>
Then there is one repeated root:
</p>

<p>r = -b/2m</p>

<p>
So the solution is:
</p>

<p>x(t) = (C<sub>1</sub> + C<sub>2</sub>t)e<sup>-bt/2m</sup></p>

<p>
This is the fastest return to equilibrium without oscillation.
</p>

<p><strong>c) Overdamped case</strong></p>
<p>
If:
</p>
<p>b² &gt; 4mk</p>

<p>
Then the roots are real and different:
</p>

<p>r<sub>1</sub> = [ -b + √(b² - 4mk) ] / 2m</p>
<p>r<sub>2</sub> = [ -b - √(b² - 4mk) ] / 2m</p>

<p>
So the solution is:
</p>

<p>x(t) = C<sub>1</sub>e<sup>r<sub>1</sub>t</sup> + C<sub>2</sub>e<sup>r<sub>2</sub>t</sup></p>

<p>
This case does not oscillate. The object returns to equilibrium slowly.
</p>

<hr>

<p><strong>3) Solve the equation numerically (RK4)</strong></p>

<p>
To solve it with RK4, we first change the second-order equation into two first-order equations.
</p>

<p>
Let:
</p>

<p>v = dx/dt</p>

<p>
Then:
</p>

<p>dx/dt = v</p>
<p>dv/dt = -(b/m)v - (k/m)x</p>

<p>
Now we have a system of two first-order differential equations.
This system can be solved step by step using the fourth-order Runge-Kutta method.
</p>

<p><strong>RK4 idea:</strong></p>
<p>
At each time step, RK4 calculates intermediate slopes and combines them
to get a more accurate value of x and v.
</p>

<p>
So in the animation or code, for each small time step:
</p>

<ul>
  <li>calculate new position x</li>
  <li>calculate new velocity v</li>
  <li>repeat for the full time interval</li>
</ul>

<hr>

<p><strong>4) Investigate the effect of parameter b</strong></p>

<p>
The damping constant <strong>b</strong> controls how quickly energy is lost.
</p>

<ul>
  <li><strong>Small b:</strong> weak damping, many oscillations</li>
  <li><strong>b = 2√(mk):</strong> critical damping</li>
  <li><strong>Large b:</strong> strong damping, no oscillation</li>
</ul>

<p>
So by moving a slider for b in an interactive program, we can clearly see
the transition between the three types of motion.
</p>

<hr>

<p><strong>5) Graph of x(t)</strong></p>

<p><strong>Underdamped:</strong></p>
<ul>
  <li>x(t) oscillates around zero</li>
  <li>the amplitude decreases with time</li>
</ul>

<p><strong>Critically damped:</strong></p>
<ul>
  <li>x(t) goes back to zero quickly</li>
  <li>there is no oscillation</li>
</ul>

<p><strong>Overdamped:</strong></p>
<ul>
  <li>x(t) also goes back to zero without oscillation</li>
  <li>but more slowly than the critically damped case</li>
</ul>

<hr>

<p><strong>6) Phase portrait</strong></p>

<p>
A phase portrait is a graph of velocity <strong>v</strong> versus position <strong>x</strong>.
</p>

<p><strong>Underdamped:</strong></p>
<p>
The curve spirals toward the origin because the system oscillates while losing energy.
</p>

<p><strong>Critically damped:</strong></p>
<p>
The curve goes to the origin without spiraling and reaches equilibrium quickly.
</p>

<p><strong>Overdamped:</strong></p>
<p>
The curve also approaches the origin without spiraling, but more slowly.
</p>

<hr>

<p><strong>Final Answer:</strong></p>

<p>
The equation
</p>

<p>m(d²x/dt²) + b(dx/dt) + kx = 0</p>

<p>
describes a damped harmonic oscillator.
Its behavior depends on the value of <strong>b² - 4mk</strong>:
</p>

<ul>
  <li><strong>Underdamped:</strong> b² &lt; 4mk → oscillates with decreasing amplitude</li>
  <li><strong>Critically damped:</strong> b² = 4mk → fastest non-oscillating motion to equilibrium</li>
  <li><strong>Overdamped:</strong> b² &gt; 4mk → no oscillation, slow return to equilibrium</li>
</ul>

<p>
For numerical simulation, we rewrite the equation as:
</p>

<p>dx/dt = v</p>
<p>dv/dt = -(b/m)v - (k/m)x</p>

<p>
and solve it using RK4.
Then we can plot:
</p>

<ul>
  <li>x(t) versus t</li>
  <li>phase portrait: v versus x</li>
</ul>