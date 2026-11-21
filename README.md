# When to Test, Repair, or Regenerate: Decision-Guided Efficient RTL Generation

**Feiyang Pan†, Shenghe Zheng†, Pengfei Xiao, Chunyan Yin, Guangbin Dou**

† Equal contribution.

**Paper:** arXiv preprint (link to be added)

## Overview

Large language models (LLMs) have shown promising capabilities in generating register-transfer-level (RTL) designs from natural-language specifications. However, achieving functional correctness often requires additional verification, repair, and regeneration, which introduce substantial inference costs.

We introduce a **decision-guided adaptive RTL generation harness** that uses a specialized decision model to determine when to test, repair, or regenerate an RTL implementation.

Our approach aims to improve functional correctness while reducing unnecessary inference expenditure.

## Method

Our framework integrates three key components:

**1. Selective Verification**

A specialized decision model evaluates the initial RTL candidate against its specification. High-scoring candidates are accepted directly, while other candidates undergo automatically generated testbench verification.

**2. Adaptive Repair and Regeneration**

When verification fails, the framework allocates the remaining generation budget between targeted repair and independent regeneration based on the initial correctness score. Repair is further guided by ranked defect categories and simulation feedback.

**3. Decision-Guided Candidate Selection**

The framework prioritizes candidates that pass generated tests and uses decision-model correctness scores to select the final RTL implementation.

## Experimental Results

We evaluate our framework on three RTL generation benchmarks:

- VerilogEval v1-Human
- VerilogEval v2
- RTLLM v2.0

With DeepSeek as the generation backbone, our framework improves mean Pass@1 by **5.4–7.1 percentage points** over initial implementations and reduces aggregate estimated inference cost by **11.0–14.3%** relative to a testbench-guided repair baseline with the same candidate cap.

## Code Availability

This repository currently serves as the project page for our paper. Implementation code and additional research materials are not included in this initial release.

## Citation

Citation information will be added following the arXiv release.
