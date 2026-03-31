<div align="center">
<hr>
<font size="6"><i><b>Stabilizing Unsupervised Self-Evolution of MLLMs via Continuous Softened Retracing reSampling</b></i></font>
<br><br>
<a href='https://arxiv.org/pdf/2503.18830'><img src='https://img.shields.io/badge/arXiv-2503.18830-b31b1b.svg'></a>
&nbsp;
<a href='https://dingwu1021.github.io/DAGait/'><img src='https://img.shields.io/badge/Project-Page-Green'></a>
<br><br>
<i>Yunyao Yu*, Zhengxian Wu*, Zhuohong Chen*, Hangrui Xu, Zirui Liao, Xiangwen Deng, Zhifang Liu, Senyuan Shi, Haoqian Wang†</i>
</div>




<img src='pics/ pipeline_arr_v2.png' style="width: 100%; height: 100%">

## 🔆 News
🔥🔥 (2025.03) Paper is available on arXiv: [DAGait: Generalized Skeleton-Guided Data Alignment for Gait Recognition](https://arxiv.org/pdf/2503.18830)

## 👀 Abstract
In the unsupervised self-evolution of Multimodal Large Language Models, the quality of feedback signals during post-training is pivotal for stable and effective learning. However, existing self-evolution methods predominantly rely on majority voting to select the most frequent output as the pseudo-golden answer, which may stem from the model's intrinsic biases rather than guaranteeing the objective correctness of the reasoning paths. To counteract the degradation, we propose \textbf{C}ontinuous \textbf{S}oftened \textbf{R}etracing re\textbf{S}ampling (\textbf{CSRS}) in MLLM self-evolution. Specifically, we introduce a Retracing Re-inference Mechanism (\textbf{RRM}) that the model re-inferences from  anchor points to expand the exploration of long-tail reasoning paths. Simultaneously, we propose Softened Frequency Reward (\textbf{SFR}), which replaces binary rewards with continuous signals, calibrating reward  based on the answers' frequency across sampled reasoning sets. Furthermore, incorporated with Visual Semantic Perturbation (\textbf{VSP}), CSRS ensures the model prioritizes mathematical logic over visual superficiality. Experimental results demonstrate that CSRS significantly enhances the reasoning performance of Qwen2.5-VL-7B on benchmarks such as MathVision. We achieve state-of-the-art (SOTA) results in unsupervised self-evolution on geometric tasks.

## ⚙️ Setup

### Install Environment via Anaconda (Recommended)
```bash
conda env create -f environment.yml
```


### 💫 Prepare training data
#### 1. Generate aligned silhouette images
You need to change the skeleton path, silhouette path, output path, and log path to your desired locations.
```bash
transform.sh
```
#### 2. Convert images to .pkl files

The silhouette path here should point to the **aligned images**.

```bash
pkl_process.sh
```

#### 3. Training
You can use the aligned pkl files to train various gait recognition networks.

```bash
CUDA_VISIBLE_DEVICES=0,1 python -m torch.distributed.launch --nproc_per_node=2 opengait/main.py --cfgs ./configs/baseline/baseline.yaml --phase train
```
For dataset samples without provided skeletons, we use [**SAPIENS**](https://github.com/facebookresearch/sapiens) to generate the corresponding skeletons from the images.

## 📜 License

This repository is released under the Apache 2.0 license.


## 😉 Citation
Please consider citing our paper if our code are useful:
```bib
@article{wu2025dagait,
      title={DAGait: Generalized Skeleton-Guided Data Alignment for Gait Recognition}, 
      author={Zhengxian Wu and Chuanrui Zhang and Hangrui Xu and Peng Jiao and Haoqian Wang},
      journal={arXiv preprint arXiv:2503.18830},
      year={2025}
}
```


## 🙏 Acknowledgements
- The codebase is based on [VeRL](https://github.com/verl-project/verl)