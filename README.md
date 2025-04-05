## How to Reproduce the baseline of the Factivity Inference Evaluation 2025

### 1. Install the SFT Framework

```bash

cd LLaMA-Factory
pip install -e ".[torch,metrics]"

```

### 2. Lora Training via Llama-Factory

```bash

llamafactory-cli train factivity_lora_sft.yaml
```

### 3. Merge the LoRA weights with the base model

```bash

llamafactory-cli export merge_config.yaml
````

### 4. Inference with the merged model

```bash

python generate.py --model_path output/qwen2-7b-factivity --data_file data/factivity_test_data.json --output_file factivity_test_results.json