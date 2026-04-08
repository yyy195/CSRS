<div align="center">
<hr>
<font size="6"><i><b>Stabilizing Unsupervised Self-Evolution of MLLMs via Continuous Softened Retracing reSampling</b></i></font>
<br><br>
<a href='https://arxiv.org/pdf/2604.03647'><img src='https://img.shields.io/badge/arXiv-2604.03647-b31b1b.svg'></a>
&nbsp;
<a href='https://yyy195.github.io/Stablizing/'><img src='https://img.shields.io/badge/Project-Page-Green'></a>
<br><br>
<i>Yunyao Yu*, Zhengxian Wu*, Zhuohong Chen*, Hangrui Xu, Zirui Liao, Xiangwen Deng, Zhifang Liu, Senyuan Shi, Haoqian Wang†</i>
</div>




<img src='pics/ pipeline_arr_v2.png' style="width: 100%; height: 100%">

## 🔆 News
🔥🔥 (2026.04) Paper is available on arXiv: [Stabilizing Unsupervised Self-Evolution of MLLMs via Continuous Softened Retracing reSampling](https://arxiv.org/pdf/2604.03647)

## 👀 Abstract
In the unsupervised self-evolution of Multimodal Large Language Models, the quality of feedback signals during post-training is pivotal for stable and effective learning. However, existing self-evolution methods predominantly rely on majority voting to select the most frequent output as the pseudo-golden answer, which may stem from the model's intrinsic biases rather than guaranteeing the objective correctness of the reasoning paths. To counteract the degradation, we propose **C**ontinuous **S**oftened **R**etracing re**S**ampling (**CSRS**) in MLLM self-evolution. Specifically, we introduce a Retracing Re-inference Mechanism (**RRM**) that the model re-inferences from  anchor points to expand the exploration of long-tail reasoning paths. Simultaneously, we propose Softened Frequency Reward (**SFR**), which replaces binary rewards with continuous signals, calibrating reward  based on the answers' frequency across sampled reasoning sets. Furthermore, incorporated with Visual Semantic Perturbation (**VSP**), CSRS ensures the model prioritizes mathematical logic over visual superficiality. Experimental results demonstrate that CSRS significantly enhances the reasoning performance of Qwen2.5-VL-7B on benchmarks such as MathVision. We achieve state-of-the-art (SOTA) results in unsupervised self-evolution on geometric tasks.

## ⚙️ Setup

### Install Environment via Anaconda (Recommended)
```bash
conda env create -f environment.yml
```


## 📜 License

This repository is released under the Apache 2.0 license.


## 😉 Citation
Please consider citing our paper if our code are useful:
```bib
@misc{yu2026stabilizingunsupervisedselfevolutionmllms,
      title={Stabilizing Unsupervised Self-Evolution of MLLMs via Continuous Softened Retracing reSampling}, 
      author={Yunyao Yu and Zhengxian Wu and Zhuohong Chen and Hangrui Xu and Zirui Liao and Xiangwen Deng and Zhifang Liu and Senyuan Shi and Haoqian Wang},
      year={2026},
      eprint={2604.03647},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2604.03647}, 
}
```


## 🙏 Acknowledgements
- The codebase is based on [VeRL](https://github.com/verl-project/verl)