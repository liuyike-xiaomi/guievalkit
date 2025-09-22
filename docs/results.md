## Agent Evaluation Results

The evaluation results are reported as Type Accuracy / Step Success Rate.

| Model                              | Android Control-Low   | Android Control-High  | GUI-Odyssey           | AiTZ                  | CAGUI-Agent           |
|------------------------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|
| UI-TARS-2B-SFT                     | 97.82 / 93.60         | 82.29 / 74.20         | 85.97 / 62.86         | 79.93 / 62.40         | 86.05 / 64.44         |
| Qwen2.5-VL-3B                      | 93.16 / 84.00         | 76.64 / 62.62         | 61.94 / 45.99         | 76.10 / 60.61         | 83.55 / 59.06         |
| Qwen2.5-VL-7B                      | 94.61 / 85.05         | 73.46 / 61.40         | 61.89 / 47.92         | 78.58 / 64.73         | 77.81 / 58.48         |
| UI-TARS-7B-SFT                     | 98.08 / 94.81         | 85.00 / 77.99         | 86.94 / 68.82         | 82.92 / 67.34         | 89.99 / 70.62         |
| UI-TARS-7B-DPO                     | 91.23 / 87.97         | 80.59 / 73.44         | 85.42 / 68.32         | 82.01 / 65.33         | 90.26 / 70.22         |
| UI-TARS-1.5-7B                     | 96.88 / 93.04         | 78.72 / 69.09         | 83.33 / 66.24         | 78.45 / 60.27         | 89.11 / 67.38         |
| MiMo-VL-7B-SFT                     | 94.84 / 90.59         | 78.19 / 67.64         | 85.87 / 62.50         | 79.91 / 63.34         | 86.34 / 64.44         |
| MiMo-VL-7B-RL                      | 95.37 / 91.32         | 77.95 / 67.50         | 85.83 / 63.05         | 80.14 / 64.71         | 85.70 / 63.91         |
| MiMo-VL-7B-SFT-2508                | 90.99 / 87.23         | 75.43 / 65.77         | 78.44 / 56.56         | 74.45 / 57.75         | 84.61 / 65.32         |
| MiMo-VL-7B-SFT-2508 (w/o thinking) | 92.84 / 89.07         | 79.02 / 68.98         | 89.45 / 70.31         | 81.69 / 66.83         | 83.08 / 63.80         |
| MiMo-VL-7B-RL-2508                 | 91.93 / 87.78         | 77.92 / 68.66         | 79.82 / 59.72         | 75.19 / 60.22         | 86.49 / 67.96         |
| MiMo-VL-7B-RL-2508 (w/o thinking)  | 94.03 / 90.23         | 79.30 / 70.04         | 85.64 / 67.08         | 79.38 / 66.91         | 79.27 / 61.60         |
| UI-Venus-Navi-7B                   | 92.17 / 86.16         | 79.05 / 68.61         | 87.30 / 71.09         | 79.06 / 65.01         | 85.16 / 64.57         |
| GUI-Owl-7B                         | 83.06 / 77.01         | 81.52 / 72.01         | 78.67 / 61.26         | 74.53 / 60.33         | 82.44 / 60.25         |
| GUI-Owl-7B (w/o thinking)          | 91.05 / 86.25         | 81.60 / 72.66         | 81.58 / 65.22         | 76.48 / 63.27         | 81.73 / 59.43         |
| MagicGUI-CPT (7B)                  | 88.91 / 81.19         | 78.50 / 67.39         | 88.84 / 74.70         | 65.45 / 44.90         | 72.05 / 46.15         |
| MagicGUI-RFT (7B)                  | 95.77 / 91.78         | 81.47 / 72.76         | 85.29 / 72.78         | 64.20 / 44.50         | 78.52 / 52.81         |
| AgentCPM-GUI-8B                    | 92.80 / 88.60         | 76.40 / 67.93         | **90.82** / **74.84** | **85.46** / **76.08** | **96.88** / **91.32** |
| GLM-4.1V-Thinking (9B)             | 86.09 / 80.66         | 67.31 / 53.02         | 72.76 / 42.57         | 68.95 / 44.01         | 85.47 / 65.48         |
| GUI-Owl-32B                        | 80.86 / 76.08         | 83.59 / 75.59         | 84.05 / 70.10         | 73.09 / 58.64         | 83.99 / 64.99         |
| GUI-Owl-32B (w/o thinking)         | 86.82 / 82.54         | 83.81 / 76.05         | 86.26 / 73.38         | 75.11 / 61.77         | 85.78 / 66.36         |
| UI-TARS-72B-SFT                    | **98.17** / **95.05** | **86.17** / **79.37** | 89.80 / 72.27         | 84.27 / 69.83         | 91.08 / 74.53         |
| UI-TARS-72B-DPO                    | 94.18 / 91.58         | 84.62 / 78.07         | 86.41 / 69.04         | 81.56 / 66.47         | 90.23 / 73.47         |
| UI-Venus-Navi-72B                  | 89.81 / 85.20         | 82.35 / 73.53         | 87.61 / 72.10         | 79.15 / 65.20         | 87.13 / 69.60         |
| GLM-4.5v (106B, 12B active)        | 86.35 / 81.37         | 71.54 / 59.15         | 75.33 / 48.90         | 70.72 / 48.52         | 87.64 / 69.26         |


Note that:
1. We find `qwen2.5-vl-32/72b-instruct` exhibits significant hallucinations in GUI agent tasks. Therefore, we exclude them from the evaluation.
2. We discard `open_app(app_name='')` action when applying UI-TARS models.
3. We discard `open_app` and `answer` actions when applying GLM-V models.
4. We discard `Launch(app='')` action when applying UI-Venus models.
5. We remove the `OPEN_APP` step when evaluating the AndroidControl benchmark.

<!--
6. The performance of MagicGUI models shows a slight dip on AC and GUI Odyssey compared to that reproduced using the source project [MagicGUI](https://github.com/MagicAgent-GUI/MagicGUI/tree/main), which can be attributed to a discrepancy between the official matching criteria and our own.
    <table>
        <thead>
          <tr>
            <th rowspan="2">Agent Models</th>
            <th colspan="2">AC-Low</th>
            <th colspan="2">AC-High</th>
            <th colspan="2">GUI-Odyssey</th>
          </tr>
          <tr>
            <th>Type</th><th>SR</th>
            <th>Type</th><th>SR</th>
            <th>Type</th><th>SR</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>MagicGUI-CPT</td>
            <td>94.5</td><td>86.7</td>
            <td>84.6</td><td>73.1</td>
            <td>90.4</td><td>73.5</td>
          </tr>
          <tr>
            <td>MagicGUI-CPT-Reproduced</td>
            <td>91.6</td><td>84.3</td>
            <td>81.6</td><td>70.8</td>
            <td>88.8</td><td>74.7</td>
          </tr>
          <tr>
            <td>MagicGUI-RFT</td>
            <td>97.2</td><td>93.5</td>
            <td>84.7</td><td>76.3</td>
            <td>-</td><td>-</td>
          </tr>
          <tr>
            <td>MagicGUI-RFT-Reproduced</td>
            <td>96.0</td><td>92.5</td>
            <td>82.7</td><td>74.5</td>
            <td>-</td><td>-</td>
          </tr>
        </tbody>
    </table>
-->
