# Table 1. V25d h8x2 token-level rollout main numeric result

Final-checkpoint h8x2 piecewise rollout on PDEBench reaction-diffusion. Each row uses 64 fixed evaluation starts. Bootstrap intervals are over the sampled starts. FNO and U-Net rows are raw/full-field context anchors and are not token-equivalent formal controls unless reduced to the same token contract.

| Model | Role | Seed | Samples | Mean MSE | Bootstrap 95% CI |
|---|---|---:|---:|---:|---:|
| MLP-stem WCA full core | formal token-level model | 15101 | 64 | `1.20737e-05` | `[1.06427e-05, 1.36155e-05]` |
| MLP-stem WCA full core | formal token-level model | 15102 | 64 | `2.27541e-05` | `[1.9785e-05, 2.61134e-05]` |
| Tokenizer-only control | negative control | 15201 | 64 | `9.3855e-05` | `[8.78088e-05, 9.99346e-05]` |
| Tokenizer-only control | negative control | 15202 | 64 | `0.000138443` | `[0.000129849, 0.000146978]` |
| Outer0 no-recursion control | negative control | 15201 | 64 | `9.60752e-05` | `[8.98242e-05, 0.000102252]` |
| Outer0 no-recursion control | negative control | 15202 | 64 | `0.000114411` | `[0.000106893, 0.000122234]` |
| FNO raw-field anchor | raw/full-field context only | 15001 | 64 | `4.28589e-05` | `[3.25206e-05, 5.38253e-05]` |
| FNO raw-field anchor | raw/full-field context only | 15002 | 64 | `7.71818e-05` | `[6.9544e-05, 8.59963e-05]` |
| U-Net raw-field anchor | raw/full-field context only | 15001 | 64 | `5.12693e-05` | `[4.41745e-05, 5.92621e-05]` |
| U-Net raw-field anchor | raw/full-field context only | 15002 | 64 | `3.8767e-05` | `[3.06355e-05, 4.76223e-05]` |

Formal interpretation: the token-level WCA rows are lower than tokenizer-only and outer0 controls in both same-family seeds. Raw/full-field FNO and U-Net rows are shown only to contextualize field-model behavior; they do not establish native/full-field visual superiority or inferiority for WCA.
