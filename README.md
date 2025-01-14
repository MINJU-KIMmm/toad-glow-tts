# 제주도 사투리 번역 및 오디오북 생성 프로젝트

## 🏝 프로젝트 개요
사멸되어가는 우리 고유 문화인 제주어를 살리고자 제주도 사투리 번역 및 오디오북 생성 프로젝트를 기획하게 되었다. 기계번역과 음성합성 두 가지 딥러닝 모델을 구현하여 기계번역을 통해 표준어에서 제주어로 번역된 사투리 텍스트를 음성합성을 통해 오디오북을 생성한다.

## 🏝 팀원 소개
<img src="https://github.com/MINJU-KIMmm/GitHubTest/blob/main/image/capstoneTeam.png"/>

## 🏝 System Architecture
<img src="https://github.com/MINJU-KIMmm/GitHubTest/blob/main/image/systemarchitecture.png"/>

## 🏝 TTS
### 1. 데이터
음성합성에는 약 14시간의 1만개의 음성데이터(.wav)를 사용한다. 
https://www.kaggle.com/bryanpark/jejueo-single-speaker-speech-dataset
### 2. Glow-TTS
TTS로는 Glow-TTS를 사용하였다. 긴 텍스트를 빠르게 합성하고 서로 다른 강세와 억양을 갖춘 발화를 생성할 수 있다는 장점이 있다.
### 3. HiFi-GAN
보코더는 HiFi-GAN을 사용할 예정이다. 다른 보코더와 비교했을 때 MOS가 높고 음성합성 빠르기도 향상되었다.

### 4. 현재 단계
<img src="https://github.com/MINJU-KIMmm/GitHubTest/blob/main/image/lossGraph.png"/>


### 5. 프로젝트 진행 상황 및 계획
<img src="https://github.com/MINJU-KIMmm/GitHubTest/blob/main/image/plan.png"/>

### 6. 기술스택
<img src="https://img.shields.io/badge/Google Colab -F9AB00?style=flat-square&logo=GoogleColab&logoColor=white"/></a>
<img src="https://img.shields.io/badge/Python -3776AB?style=flat-square&logo=Python&logoColor=white"/>
<img src="https://img.shields.io/badge/Jupyter -F37626?style=flat-square&logo=Jupyter&logoColor=white"/>
<img src="https://img.shields.io/badge/TensorFlow -181717?style=flat-square&logo=TensorFlow&logoColor=white"/>
<img src="https://img.shields.io/badge/GitHub -181717?style=flat-square&logo=GitHub&logoColor=white"/>

### 7. 폴더 구조
<pre>
<code>
.
└── content
    ├── TTS
    │   ├── TTS
    │   │   ├── bin
    │   │   ├── config
    │   │   ├── server
    │   │   │   ├── static
    │   │   │   └── templates
    │   │   ├── speaker_encoder
    │   │   │   └── utils
    │   │   ├── tts
    │   │   │   ├── configs
    │   │   │   ├── datasets
    │   │   │   ├── layers
    │   │   │   │   ├── align_tts
    │   │   │   │   ├── feed_forward
    │   │   │   │   ├── generic
    │   │   │   │   ├── glow_tts
    │   │   │   │   │   └── monotonic_align
    │   │   │   │   └── tacotron
    │   │   │   ├── models
    │   │   │   ├── tf
    │   │   │   │   ├── layers
    │   │   │   │   │   └── tacotron
    │   │   │   │   ├── models
    │   │   │   │   └── utils
    │   │   │   └── utils
    │   │   │       └── text
    │   │   │           └── chinese_mandarin
    │   │   ├── utils
    │   │   └── vocoder
    │   │       ├── configs
    │   │       ├── datasets
    │   │       ├── layers
    │   │       ├── models
    │   │       ├── tf
    │   │       │   ├── layers
    │   │       │   ├── models
    │   │       │   └── utils
    │   │       └── utils
    │   ├── filelists
    │   │   └── wavs
    │   ├── images
    │   ├── notebooks
    │   │   └── dataset_analysis
    │   ├── recipes
    │   │   └── ljspeech
    │   │       └── tacotron2-DDC
    │   └── tests
    │       ├── bash_tests
    │       ├── data
    │       │   └── ljspeech
    │       │       ├── phoneme_cache
    │       │       └── wavs
    │       ├── inputs
    │       ├── tts_tests
    │       └── vocoder_tests
    └── data
        ├── glowtts-v2
        │   ├── glowtts-v2-December-01-2021_05+15AM-3aa165a
        │   │   └── test_audios
        │   │       ├── 26027
        │   │       ├── 26054
        │   │       ├── 26081
        │   │       ├── 26108
        │   │       ├── 26135
        │   │       ├── 26162
        │   │       ├── 26189
        │   │       ├── 26216
        │   │       ├── 26243
        │   │       ├── 26270
        │   │       ├── 26297
        │   │       ├── 26324
        │   │       ├── 26351
        │   │       ├── 26378
        │   │       ├── 26405
        │   │       ├── 26432
        │   │       ├── 26459
        │   │       ├── 26486
        │   │       ├── 26513
        │   │       ├── 26540
        │   │       ├── 26567
        │   │       ├── 26594
        │   │       ├── 26621
        │   │       ├── 26648
        │   │       ├── 26675
        │   │       ├── 26702
        │   │       ├── 26729
        │   │       ├── 26756
        │   │       ├── 26783
        │   │       ├── 26810
        │   │       ├── 26837
        │   │       ├── 26864
        │   │       ├── 26891
        │   │       ├── 26918
        │   │       ├── 26945
        │   │       └── 26972
        │   ├── glowtts-v2-November-28-2021_05+54PM-3aa165a
        │   ├── glowtts-v2-November-28-2021_05+55PM-3aa165a
        │   ├── glowtts-v2-November-28-2021_05+59PM-3aa165a
        │   └── glowtts-v2-November-28-2021_06+16PM-3aa165a
        └── hifigan-v2
            └── hifigan-v2-November-28-2021_06+06PM-3aa165a
</code>
</pre>
