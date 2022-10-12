# riskparity.rs
Implementations of risk parity portfolios in Rust

## Example

```{rust}
use riskparity::vanilla::compute_riskparity_ccd_choi;

fn main() {
    let cov = ndarray::arr2(&[
        [1.0, 0.0015, -0.0119],
        [0.0015, 1.0, -0.0308],
        [-0.0119, -0.0308, 1.0],
    ]);
    let budget = ndarray::arr1(&[0.1594, 0.0126, 0.8280]);
    let maxiter = 100;
    let tol = 1e-6;
    println!(
        "{}",
        compute_riskparity_ccd_choi(&cov, &budget, maxiter, tol)
    );
    // [0.279862, 0.087749, 0.632388]
}
```
