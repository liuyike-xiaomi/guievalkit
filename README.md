# A Unified Toolkit for Evaluating GUI Agents

GUIEvalKit is an open-source evaluation toolkit for GUI agents, allowing practitioners to easily assess these agents on various (offline) benchmarks. The main goal is to provide an easy-to-use, open-source toolkit that simplifies the evaluation process for researchers and developers, while ensuring that evaluation results can be easily reproduced.

## Requirements and Installation

This work has been tested in the following environment:
* `python == 3.10.12`
* `torch == 2.7.1+cu126`
* `transformers == 4.56.1`
* `vllm == 0.10.1`

## Supported Models

| Model                                                            | Model Name                                    | Organization |
|------------------------------------------------------------------|-----------------------------------------------|--------------|
| [Qwen2.5-VL](https://github.com/QwenLM/Qwen2.5-VL)               | `qwen2.5-vl-3/7/32/72b-instruct`              | Alibaba      |
| [GUI-Owl](https://github.com/X-PLUG/MobileAgent)                 | `gui-owl-7/32b`                               | Alibaba      |
| [UI-Venus](https://github.com/inclusionAI/UI-Venus)              | `ui-venus-navi-7/72b`                         | Ant Group    |
| [UI-TARS](https://github.com/bytedance/UI-TARS)                  | `ui-tars-2/7/72b-sft`, `ui-tars-7/72b-dpo`    | Bytedance    |
| [UI-TARS-1.5](https://github.com/bytedance/UI-TARS)              | `ui-tars-1.5-7b`                              | Bytedance    |
| [AgentCPM-GUI](https://github.com/OpenBMB/AgentCPM-GUI)          | `agentcpm-gui-8b`                             | ModelBest    |
| [MiMo-VL](https://github.com/XiaomiMiMo/MiMo-VL)                 | `mimo-vl-7b-sft/rl`, `mimo-vl-7b-sft/rl-2508` | Xiaomi       |
| [GLM-V](https://github.com/zai-org/GLM-V)                        | `glm-4.1v-9b-thinking`, `glm-4.5v`            | Zhipu AI     |
| [MagicGUI](https://github.com/MagicAgent-GUI/MagicGUI/tree/main) | `MagicGUI-CPT`, `MagicGUI-RFT`                | Honor        |

## Supported Benchmarks

| Dataset                                                                                          | Task Name                  | Task      | Description                        |
|--------------------------------------------------------------------------------------------------|----------------------------|-----------|------------------------------------|
| [AndroidControl](https://github.com/google-research/google-research/tree/master/android_control) | `androidcontrol_low/high`  | Agent     | 1680 episodes, (10814 - 653) steps |
| [CAGUI](https://huggingface.co/datasets/openbmb/CAGUI)                                           | `cagui_agent`              | Agent     | 600 episodes, 4516 steps           |
| [GUI Odyssey](https://github.com/OpenGVLab/GUI-Odyssey)                                          | `gui_odyssey`              | Agent     | 1933 episodes, 29426 steps         |
| [AiTZ](https://github.com/IMNearth/CoAT)                                                         | `aitz`                     | Agent     | 506 episodes, 4724 steps           |

## Data Preparation

Please follow the [instructions](./data/README.md) to download and preprocess the datasets.

## Data & Model Registration

Please update the files [dataset_info.json](./config/dataset_info.json) and [model_info.json](./config/model_info.json) with your own information.

## Evaluation

```bash
python3 run.py \
  --model agentcpm-gui-8b \
  --dataset cagui_agent \
  --mode all \
  --outputs outputs/agentcpm-gui-8b/cagui_agent \
  --use-vllm
```
**Arguments:**
- `--model (str)`: Set the model name that is supported in GUIEvalKit (defined in `config/model_info.json`).
- `--dataset (str)`: Set the benchmark name that is supported in GUIEvalKit (defined in `config/dataset_info.json`).
- `--mode (str, default to 'all', choices are ['all', 'infer', 'eval'])`: When `mode` set to `all`, will perform both inference and evaluation; when set to `infer`, will only perform the inference; when set to `eval`, will only perform the evaluation.
- `--outputs (str, default to './outputs')`: The directory to save evaluation results.
- `--batch-size (int, default to 64)`: The batch size used for inference.
- `--no-think`: Use this argument if you want to disable the thinking mode (if applicable).
- `--use-vllm`: Use this argument if you want to inference with `vllm`, otherwise `transformers` will be adopted.
- `--over-size`: Use this argument for deploying large models on four GPUs and inferring with `vllm`. 

**Please check [here](./docs/results.md) for the detailed evaluation results.**

<!--

## Development Guide

To add new GUI agents and benchmarks to GUIEvalKit, please refer to the [Development Guide](./docs/development.md).

-->

## Acknowledgement

This repo benefits from [AgentCPM-GUI/eval](https://github.com/OpenBMB/AgentCPM-GUI/tree/main/eval) and [VLMEvalKit](https://github.com/open-compass/VLMEvalKit). Thanks for their wonderful works.
