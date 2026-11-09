[README.md](https://github.com/user-attachments/files/34603321/README.md)
# Instrumental Variables: Weak Instruments, Compliers and the Exclusion Restriction

## Objective

I explored how instrument strength, the population being studied and violations of the exclusion restriction affect IV estimates.

## Methodology

- Simulated instruments of different strengths and compared OLS and 2SLS estimates across 500 samples.
- Replicated Card’s (1995) schooling analysis using college proximity as an instrument.
- Examined whose schooling decisions the instrument changes and what that means for interpreting the estimate.
- Added a direct effect from the instrument to the outcome to check sensitivity to exclusion violations.
- Built a 2SLS function using two OLS regressions and checked it against `linearmodels`.

## Key Findings

With a median first-stage F of 0.5, I found a median 2SLS estimate of 2.038, close to OLS at 1.998 rather than the true effect of 1.0. Among significant estimates, 98.1% were more than 0.5 away from the truth.

For Card’s data, I found a first-stage F of 16.7, an OLS schooling coefficient of 0.0740 and a 2SLS coefficient of 0.1323. The IV estimate applies to people whose schooling changes because of college proximity, assuming the instrument is valid.

Adding a direct instrument effect of 0.25 moved the simulated estimate from 0.838 to 1.395. My own 2SLS function also passed the checks against `linearmodels`.
