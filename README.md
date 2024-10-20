<div align=center><img src="assets/logo.jpg" height="100%" width="90%"/></div>

<h2 align="center"> <a href="https://arxiv.org/abs/2410.08565">Baichuan-Omni Technical Report</a></h2>
<h5 align="center"> If our project helps you, please give us a star ⭐ and cite our <a href="#citation">paper</a>!</h2>
<h5 align="center">

<!-- TODO：改成我们自己的链接 -->

[![hf_space](https://img.shields.io/badge/🤗-Paper%20In%20HF-red.svg)](https://huggingface.co/papers/2410.08565)
[![hf_checkpoint](https://img.shields.io/badge/🤗-Checkpoints-9C276A.svg)](https://github.com/westlake-baichuan-mllm/bc-omni)
[![arxiv](https://img.shields.io/badge/Arxiv-2410.08565-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2410.08565)
[![visitor](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fwestlake-baichuan-mllm%2Fbc-omni&count_bg=%2379C83D&title_bg=%23454343&icon=&icon_color=%23E7E7E7&title=visitor&edge_flat=false)](https://hits.seeyoufarm.com)
<!-- [![License](https://img.shields.io/badge/License-Apache%202.0-yellow)](https://github.com/DAMO-NLP-SG/VideoLLaMA2/blob/main/LICENSE) -->
[![GitHub issues](https://img.shields.io/github/issues/westlake-baichuan-mllm/bc-omni?color=critical&label=Issues)](https://github.com/westlake-baichuan-mllm/bc-omni/issues?q=is%3Aopen+is%3Aissue)
[![GitHub closed issues](https://img.shields.io/github/issues-closed/westlake-baichuan-mllm/bc-omni?color=success&label=Issues)](https://github.com/westlake-baichuan-mllm/bc-omni/issues?q=is%3Aissue+is%3Aclosed) <br>


<div style="display: flex; justify-content: center;">  
    <img src="assets/lidar.png" style="width: 48%; height: auto;"/>
    <img src="assets/lidar_avg.png" style="width: 48%; height: auto;"/>  
</div>

## News
- **[2024/10/11]** 🔥 We have released technical report of **Baichuan-Omni**. See [here](https://arxiv.org/abs/2410.08565)!

## Introduction
The salient multimodal capabilities and interactive experience of GPT-4o highlight its critical role in practical applications, yet it lacks a high-performing open-source counterpart.

In this paper, we introduce Baichuan-Omni, the first high-performing open-source Multimodal Large Language Model (MLLM) adept at concurrently processing and analyzing modalities of image, video, audio, and text, while delivering an advanced multimodal interactive experience. We propose an effective multimodal training schema starting with 7B model and proceeding through two stages of multimodal alignment and multitask fine-tuning across audio, image, video, and text modal. 

This approach equips the language model with the ability to handle visual and audio data effectively. Demonstrating strong performance across various omni-modal and multimodal benchmarks, we aim for this contribution to serve as a competitive baseline for the open-source community in advancing multimodal understanding and real-time interaction.

## Architecture & Training Schema

The training pipeline is divided into two phases:

<div align=center><img src="assets/pipeline.svg" height="100%" width="90%"/></div>

**Phase 1: Multimodal Alignment Pretraining.** The pre-training and alignment processes consist of Image-Language, Video-Language, and Audio-Language branches.
  - The Image-Language branch utilizes a visual encoder to process images and undergoes training in three stages, focusing on image captioning, visual question answering tasks, and further enhancing alignment with the large language model (LLM).
  - The Video-Language branch builds on the Image-Language branch, using the same visual encoder and video projector, and trains with a mix of image-text and video-text pairs.
  - The Audio-Language branch incorporates the Whisper-large-v3 model's audio encoder and a novel convolutional-gated MLP projector, replacing traditional pooling methods to retain more audio information. Finally, the Omni-Alignment stage integrates all branches, training on high-quality multimodal data pairs to enhance the model's multimodal understanding capabilities.


**Phase 2: Multimodal Supervised Fine-Tuning.** The multimodal supervised fine-tuning process designed to enhance the model's ability to follow complex instructions across various tasks, utilizing a dataset of over 600K pairs spanning multiple modalities.
  - The text-only data encompasses a wide range of tasks, emphasizing complex, multi-step instructions.
  - For image understanding, we employed the vFLAN dataset, applying a loss-based filtering method to improve data quality and translating the data into Chinese for better alignment.
  - The video understanding component is sourced from the VideoInstruct100K dataset, where we implemented semantic deduplication and translation to diversify the instructions.
  - In the audio understanding part, we generated audio using text-to-speech technology, ensuring quality through transcription verification and supplementing it with human-recorded samples to capture diverse dialects.


## Experimental Results

We conducted a comprehensive evaluation across various modalities, including language, image understanding, video understanding, and audio understanding. The results indicate that Baichuan-Omni demonstrates superior capabilities in omni-modal comprehension.

### Language understanding

<div align=center><img src="assets/lang-perf.png" height="100%" width="80%"/></div>

### Image understanding

<div align=center><img src="assets/img-perf-1.png" height="100%" width="90%"/></div>

<div align=center><img src="assets/img-perf-2.png" height="100%" width="90%"/></div>

### Video understanding

<div align=center><img src="assets/video-perf-1.png" height="100%" width="90%"/></div>

<div align=center><img src="assets/video-perf-2.png" height="100%" width="90%"/></div>

### Audio understanding

<div align=center><img src="assets/audio-perf-1.png" height="100%" width="90%"/></div>

<div align=center><img src="assets/audio-perf-2.png" height="100%" width="90%"/></div>

## Demo

https://github.com/user-attachments/assets/00cad3cd-2193-4298-afd5-849c2da01a83

> Coming soon & Stay tuned! 😉
## Requirements and Installation

## Model Zoo

## Evaluation

## Inference

## Citation

```bibtex
@article{li2024baichuanomni,  
  title={Baichuan-Omni Technical Report},  
  author={Li, Yadong and Sun, Haoze and Lin, Mingan and Li, Tianpeng and Dong, Guosheng and Zhang, Tao and Ding, Bowen and Song, Wei and Cheng, Zhenglin and Huo, Yuqi and Chen, Song and Li, Xu and Pan, Da and Zhang, Shusen and Wu, Xin and Liang, Zheng and Liu, Jun and Zhang, Tao and Lu, Keer and Zhao, Yaqi and Shen, Yanjun and Yang, Fan and Yu, Kaicheng and Lin, Tao and Xu, Jianhua and Zhou, Zenan and Chen, Weipeng},  
  journal={arXiv preprint arXiv:2410.08565},  
  year={2024}  
}
```
