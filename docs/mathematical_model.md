
# Mathematical Model

## 1. Transmitted signal

The transmitted QPSK symbol is:

s_k = A exp(j phi_k)

where:
- A is the symbol amplitude.
- phi_k is the transmitted symbol phase.
- j is the imaginary unit.

## 2. Received signal

The received signal is:

r_k = s_k exp(j theta_k) + n_k

where:
- theta_k is the carrier phase noise.
- n_k is complex additive white Gaussian noise.

## 3. State vector

The state vector is:

x_k = [theta_k, omega_k]^T

where:
- theta_k is carrier phase.
- omega_k is phase increment per symbol.

## 4. State transition

x_k = F x_(k-1) + w_k

F = [[1, 1],
     [0, 1]]

The process noise is:

w_k ~ N(0, Q)

## 5. Observation model

z_k = h(x_k) + v_k

h(x_k) = [
    Re(s_k exp(j theta_k)),
    Im(s_k exp(j theta_k))
]^T

The measurement noise is:

v_k ~ N(0, R)

## 6. Estimation objective

Estimate theta_k recursively from noisy
in-phase and quadrature observations.
