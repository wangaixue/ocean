# Learning Object-aware Anchor-free Networks for Real-time Object Tracking

- Code and models for double blind review in ECCV2020. 

## Introduction
Anchor-based Siamese trackers have witnessed tremendous success in visual tracking, yet their robustness still leaves a gap with recent state-of-the-art approaches. We find the underlying reason is that the regression network in anchor-based methods is only trained on the positive anchor boxes. This mechanism makes it difficult to refine the anchors whose overlap with the target objects are small. 
  
Our proposals mitigate the problem by,
1) We propose a novel anchor-free algorithm for realtime visual tracking. It is capable of rectifying the imprecise bounding-box predictions whose overlap with the target objects are small.

2)  We introduce an adaptive feature alignment mechanism to set up a correspondence between the objectaware features and the predicted bounding boxes. This leads to a more robust classification of foreground objects and background clutters.


<div align="center">
  <img src="demo/ocean.gif" width="800px" />
  <!-- <p>Example SiamFC, SiamRPN and SiamMask outputs.</p> -->
</div>


<!-- ## Results

| Benchmark  | VOT18 | VOT19 | OTB15 | GOT10K | LASOT| 
| :------ | :------: | :------: | :------: | :------: | :------: |
| Performance  | 0.467 | 0.327 | 0.673 | 0.592 | 0.526 |  
| Raw Results|:paperclip: [VOT18](https://drive.google.com/file/d/1VRRAzbePYSqR1O0abR1yINVp561M3mV_/view?usp=sharing) |:paperclip: [VOT19](https://drive.google.com/file/d/1Y-0eBRsqTsfajjJDabkcjCnijtzRoOEQ/view?usp=sharing)  |:paperclip:[OTB15](https://drive.google.com/file/d/17DJRAn-QnTMjnHED8j9AD3qIV2iFx0AJ/view?usp=sharing)  |:paperclip:[GOT10K](https://drive.google.com/file/d/1BStCIGqMaobfEndbqlbhePkGzTcSrFS2/view?usp=sharing)  |:paperclip:[LASOT](https://drive.google.com/file/d/1V8rX1Zkxk1R6Z9q0W4Z9NSx63jIPTFyh/view?usp=sharing) |  
 -->


## Quick Start
### Installation

```
bash install.sh ocean
```

### Preparation
The test datasets should be arranged in `dataset` directory, and the pre-trained models should be arranged in `snapshot` directory.

```
${Tracking_ROOT}
|—— experimnets
|—— lib
|—— snapshot
  |—— xxx.model
|—— dataset
  |—— VOT2019.json 
  |—— VOT2019
     |—— videos...
|—— ...

```
<!-- Download [pre-trained models](https://drive.google.com/drive/folders/1nkSTnyLQidpW67AdD8T7BVsbgrY2_iYt?usp=sharing) and [json](https://drive.google.com/drive/folders/10hDmCLLo0c5Hs12kqB--Ctj95UTiFVrH?usp=sharing) files here. -->

Download [pre-trained models](https://drive.google.com/file/d/1cl5QCasDguiw5RxoIFqBVGTsLfV2cNkm/view?usp=sharing) and [json](https://drive.google.com/open?id=1S-RkzyMVRFWueWW91NmZldUJuDyhGdp1) files here.

<!-- https://drive.google.com/file/d/1bJh5-vdscBHciboAuBG_mTmD-ZvFf8M2/view?usp=sharing -->

### Test
```
python ocean_tracking/test_ocean.py --arch Ocean --dataset VOT2018
```

### Evaluation
```
python lib/eval_toolkit/bin/eval.py --dataset_dir dataset --dataset VOT2018 --tracker_result_dir result/VOT2018 --trackers Ocean
```

<!-- - For other benchmarks, use model [here](https://drive.google.com/drive/folders/1nkSTnyLQidpW67AdD8T7BVsbgrY2_iYt?usp=sharing) and please test the results files in the official toolkit.   -->

<!-- Download [pre-trained models](https://drive.google.com/drive/folders/1nkSTnyLQidpW67AdD8T7BVsbgrY2_iYt?usp=sharing) and [json](https://drive.google.com/drive/folders/10hDmCLLo0c5Hs12kqB--Ctj95UTiFVrH?usp=sharing) files here. -->
 
<!-- ## Parameter Tuning Toolkit :tada::tada:
Lift is short, let's release our hands and brain. With our toolkit, you don't need to analysz how each hyper-parameter influence the final result. **Just a quick click!!** 
```
Coming Soon...
```
Now you can go to bed for a good sleep. The favorable results will come with dawn. -->

### Train

Please follow the tutorial [here](https://github.com/cvsubmit/ocean/blob/master/train.md).






