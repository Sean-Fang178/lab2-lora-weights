# Lab2 LoRA weights (113304035)

LoRA weights for NYCU Image and Video Generation (2026 Fall), Lab 2. Base model: `CompVis/stable-diffusion-v1-4`.

| Folder | Task | Training |
|---|---|---|
| `task2-1_style_lora/` | 2-1 style LoRA | `sample_data/artistic-custom` (4 images), 300 epochs / 1200 steps |
| `task2-2_dreambooth_cat_lora/` | 2-2 DreamBooth + LoRA | `sample_data/dreambooth-cat` (4 images), prompt "a photo of a sks cat", 500 steps |

Usage (`lora_inference.ipynb`): set `lora_path` to one of the folders above.

```python
pipe = StableDiffusionPipeline.from_pretrained("CompVis/stable-diffusion-v1-4", torch_dtype=torch.float16)
pipe.load_lora_weights("task2-2_dreambooth_cat_lora")
image = pipe("a photo of sks cat on the beach").images[0]
```
