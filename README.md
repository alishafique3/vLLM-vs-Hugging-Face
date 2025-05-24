# vLLM vs. Hugging Face for High-Performance Offline LLM Inference

Offline inference—such as batch generation, document processing, or static content creation—demands high throughput and cost efficiency. This benchmark compares two leading frameworks:

- 🤗 **Hugging Face Transformers**
- ⚡ **[vLLM](https://github.com/vllm-project/vllm)** (optimized engine with PagedAttention)

---

### 💻 Experiment Setup

- **Model**: `meta-llama/Llama-3.2-3B-Instruct`
- **Hardware**: NVIDIA L4 GPU on Google Vertex AI Workbench
- **Batch Sizes**: 4, 8, 16, 32
- **Libraries**:
  - `transformers==4.47.1`
  - `vllm` (latest stable)

---

### 📊 Benchmark Results

| Batch Size | vLLM (sec) | Hugging Face (sec) |
|------------|------------|--------------------|
| 4          | 2.32       | 5.32               |
| 8          | 2.51       | 7.24               |
| 16         | 3.01       | 9.50               |
| 32         | 3.38       | 12.90              |

*IFT = Inference Time*

---

### 🔍 Key Takeaways

- **vLLM is 2–4× faster** than Hugging Face on batch workloads.
- Uses **PagedAttention** to optimize KV cache memory.
- Better **scalability and GPU utilization** for large-scale offline inference.
- Hugging Face offers more flexibility for research and prototyping.

---

### ✅ Conclusion

If you're running **production-scale, high-throughput offline generation**, vLLM offers **superior performance and efficiency** over the default Hugging Face inference stack.

