# Baichuan-Omni: 
<!-- TODOs: Replace vita staff with Baichuan -->
## 1. Introduction
Baichuan-Omni is a high-performing open-source Multimodal Large Language Model (MLLM) developed by Baichuan Ltd and the School of Engineering at Westlake University. It delivers an advanced multimodal interactive experience in image, video, audio, and text. In the project, we propose an effective multimodal training schema starting with the Baichuan 7B model and proceeding through two stages of multimodal alignment and multitask fine-tuning
across audio, image, video, and text modal. This approach equips the language model with the ability to handle visual and audio data effectively. Demonstrating strong performance across various unimodal and multimodal benchmarks, we aim for this contribution to serve as a competitive baseline for the open-source community in advancing multimodal understanding and real-time interaction.
<!-- <div style='display:flex; gap: 0.25rem; '>
<a href=''><img src='https://img.shields.io/badge/SALMONN_13B-Demo-blue'></a>
<a href=''><img src='https://img.shields.io/badge/SALMONN_7B-Demo-orange'></a>
<a href=''><img src='https://img.shields.io/badge/SALMONN_paper-PDF-green'></a>
<a href=''><img src='https://img.shields.io/badge/huggingface-checkpoint-yellow'></a> 
</div> -->

<!-- <div style='display:flex; gap: 0.25rem; '>
<a href='https://bytedance.github.io/SALMONN/'><img src='https://img.shields.io/badge/SALMONN_13B-Demo-blue'></a>
<a href='https://huggingface.co/spaces/tsinghua-ee/SALMONN-7B-gradio'><img src='https://img.shields.io/badge/SALMONN_7B-Demo-orange'></a>
<a href='https://openreview.net/pdf?id=14rn7HpKVk'><img src='https://img.shields.io/badge/SALMONN_paper-PDF-green'></a>
<a href='https://openreview.net/pdf?id=nYsh5GFIqX'><img src='https://img.shields.io/badge/video_SALMONN_paper-PDF-green'></a>
<a href='https://huggingface.co/tsinghua-ee/SALMONN'><img src='https://img.shields.io/badge/huggingface-checkpoint-yellow'></a> 
</div> -->

## 2. News
- [TBD] We have released technical report for **Baichuan-Omni**! See [here](https://www.overleaf.com/project/66e3d40121950eb2655a99c5)!

## 3. Structure & Training schema
In terms of interactivity, the model initially predicts the start and end of audio inputs. During this period, incoming images and videos are encoded into features and fed into the MLLM in a streaming fashion to calculate attention. The audio features are then input into the MLLM for inference following the end of the audio input,
facilitating streaming input of audio and video.
<div align=center><img src="asserts/pipeline.svg" height="100%" width="75%"/></div>

**Pretraining.** During the pretraining phase, we initially train a vision-language model using extensive image-text data, followed by training an audio-language model with ASR data. Subsequently, we integrate high-quality images, audio, and video data for comprehensive multimodal alignment. 

**Fine-tuning.** We synthesize a subset of cross-modal interaction
data to blend with existing high-quality datasets. From this enriched dataset, we select a subset of
data that the model is already capable of handling and proceed with multimodal multitask fine-tuning.
This process aims to enhance the model’s adherence to omni-modal instructions.



## 4. Experimental Results
### 4.1 Language understanding
<div align=center><img src="asserts/LanguageUnderstand.jpg" height="100%" width="80%"/></div>


### 4.2 Image understanding


### 4.3 Video understanding


### 4.4 Audio understanding