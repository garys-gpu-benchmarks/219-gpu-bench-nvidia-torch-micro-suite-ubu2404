# Results: 219 PyTorch Microkernel Suite

**Main goal:** Measure PyTorch GEMM and Conv2d microkernel time, TFLOPS, and bandwidth  
**Tools:** Run the PyTorch microkernel suite through scripts/gemm.py and scripts/conv2d.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_140 · recorded 2026-11-13). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 PCIe (81559 MiB) · Intel(R) Xeon(R) Platinum 8352Y CPU @ 2.20GHz · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.91.07
- **Run:** 2026-11-13T20:55:58Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 02:15 · benchmark 00:08 · whole run 02:37
- **Source:** run 219_20261113_205558
- **Command:** `bash run_benchmark.sh --smoke --device-id 0 --dtype fp16 --input-shape 1,3,32,32 --M 64 --N 64 --K 64 --warmup-iters 2 --num-iterations 5 --seed 42`

| # | Metric | Result |
|---|---|---|
| 1 | GEMM execution time, us (gemm_time_usec) | 23.63082 |
| 2 | GEMM throughput, TFLOPS (gemm_tflops) | 0.022187 |
| 3 | GEMM minimum traffic, GB/s (gemm_bandwidth_gb_s) | 1.039998 |
| 4 | Conv2d execution time, us (conv_time_usec) | 40.594209 |
| 5 | Conv2d throughput, TFLOPS (conv_tflops) | 0.010897 |
| 6 | Conv2d minimum traffic, GB/s (conv_bandwidth_gb_s) | 0.565598 |
<!-- /profile:smoke -->
