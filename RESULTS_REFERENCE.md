# Results: 219 PyTorch Microkernel Suite

**Main goal:** Measure PyTorch GEMM and Conv2d microkernel time, TFLOPS, and bandwidth  
**Tools:** Run the PyTorch microkernel suite through scripts/gemm.py and scripts/conv2d.py

Reference results from the validation run on the system shown in each section (recorded 2026-11-22). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 80GB HBM3 (81559 MiB) · Intel(R) Xeon(R) Platinum 8470 · Ubuntu 24.04.5 LTS · kernel 6.8.0-149-generic · driver 595.112.07
- **Run:** 2026-11-22T14:34:52Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 01:26 · benchmark 00:05 · whole run 01:39
- **Source:** run 219_20261122_143452
- **Command:** `bash run_benchmark.sh --smoke --device-id 0 --dtype fp16 --input-shape 1,3,32,32 --M 64 --N 64 --K 64 --warmup-iters 2 --num-iterations 5 --seed 42`

| # | Metric | Result |
|---|---|---|
| 1 | GEMM execution time, us (gemm_time_usec) | 14.036999 |
| 2 | GEMM throughput, TFLOPS (gemm_tflops) | 0.03735 |
| 3 | GEMM minimum traffic, GB/s (gemm_bandwidth_gb_s) | 1.750802 |
| 4 | Conv2d execution time, us (conv_time_usec) | 14.581799 |
| 5 | Conv2d throughput, TFLOPS (conv_tflops) | 0.030337 |
| 6 | Conv2d minimum traffic, GB/s (conv_bandwidth_gb_s) | 1.574566 |
<!-- /profile:smoke -->
