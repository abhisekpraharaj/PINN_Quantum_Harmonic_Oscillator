# PINN_Quantum_Harmonic_Oscillator
## Mathematics
for a Quantum harmonic oscillator if we need to solve the schrodinger equation:

### $H = \frac{p^2}{2m} + \frac{1}{2} m \omega^2 x^2$

if we solve the schrodinger equation it will be like this:

### $\left( \frac{-\hbar^2}{2m} \frac{d^2}{dx^2} + \frac{1}{2} m \omega^2 x^2 \right) \psi(x) = E \psi(x)$

### where \omega =  $frac{k}{m}$

we know the Energy for a QHO will be in packet format or quantised:
### $E = (n+ \frac{1}{2}) \hbar \omega$

and the solution for wave function will be:
### $\psi(x) = (\frac {m \omega} {\pi \hbar})^\frac{1}{4} \frac{1}{\sqrt(2^n n!)} H_{n}(\frac{m \omega}{\hbar} x) exp(\frac{-m \omega x^2}{2\hbar})$

#### Important: Physics Loss which need to be implemented in it
now since we get the PDE, now we have to calculate the physics/pde loss, here is the definition of physics_loss
### $\left( \frac{-\hbar^2}{2m} \frac{d^2}{dx^2} + \frac{1}{2} m \omega^2 x^2 \right) \psi(x) - E \psi(x) = $pde loss$$

next we define the boundary loss, as our wavefunction should be 0 around boundary and use it by adding it to our loss term.

### what's the change!
In Nomarl Neural Network(NNN) models we dont incorporate these losses, only the data loss is used there. Since we have an upper hand of describing the physical systems, a model with physics incorporated loss with data loss (PINN) is expected to behave better rather than a model learning from only data loss.

PINN's way of learning will be better of us if we have a data from a certain phenomena which we need to predict its outcomes, then with very low input data and physics knowledge behind the phenomena, expect to get use better predictions like spatio temporal data, MRI of patients who has diagnosed with level 1 of a disease etc.
## Work Flow
I will let you more on the data , and how to do it here:

Total Loss = Data loss + Physics Loss

$\mathcal{L}_{\text{physics}} = \frac{1}{M} \sum_{i=1}^{M} \left( -\frac{\hbar^2}{2m} \frac{d^2 \psi(x_i)}{dx^2} + V(x_i) \psi(x_i) - E \psi(x_i) \right)^2$



 








