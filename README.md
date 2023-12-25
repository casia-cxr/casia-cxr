# An Open Dataset of Chest X-rays with Benchmarks on Automatic Radiology Report Generation in French

## 📔 Introduction
Medical report generation (MRG), which aims to automatically generate a textual description of a specific medical image (e.g., a chest X-ray), has recently received increasing research interest. Building on the success of image captioning, medical report generation has become achievable. However, generating language-specific radiology reports is a challenge for data-driven models due to their reliance on paired image-report datasets, which are labor-intensive, time-consuming, and costly. In this paper, we introduce a chest X-ray benchmark dataset, namely *CASIA-CXR* consisting of high-resolution chest radiographs associated with medical reports originally written in French. To the best of our knowledge, this is the first public chest radiograph dataset with medical reports in this particular language. Importantly, we propose a simple yet effective multimodal encoder-decoder contextually-guided framework for medical report generation in French. We validated our framework using intra-language and cross-language evaluations, complemented by expert evaluation performed by radiologists. The dataset is freely available at https://github.com/casia-cxr/

## 📔 Links
* To download a sample of our dataset: [Link](https://metmer.net/CASIA-CXR/Download/Download.php)
* To request the full dataset, please contact us at: [Link](https://www.casia-cxr.net/Downloads.html#RequestCompleteDataset)

## 📔 Tables
📑 Disease Classification Performance
|  | Disease | Accuracy | Precision | Recall | F1-Score | Support |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Global Labels | Cardiomegaly | 0.830 | 0.937 | 0.825 | 0.877 | 3,756 |
|  | Pneumothorax | 0.823 | 0.935 | 0.811 | 0.868 | 2,000 |
|  | Pneumonia | 0.712 | 0.817 | 0.779 | 0.797 | 2,000 |
|  | Pleural Effusion | 0.660 | 0.841 | 0.598 | 0.698 | 2,000 |
|  | Mass | 0.582 | 0.692 | 0.630 | 0.659 | 1,355 |
| Local  Labels | Pulmonary Opacity | 0.580 | 0.373 | 0.460 | 0.412 | 680 |
|  | Emphysema | 0.811 | 0.701 | 0.748 | 0.724 | 595 |
|  | Edema | 0.602 | 0.655 | 0.482 | 0.555 | 609 |
|  | Atelectasis | 0.715 | 0.722 | 0.701 | 0.711 | 554 |
|  | Lung Tumor | 0.721 | 0.843 | 0.717 | 0.775 | 584 |
|  | Calcification | 0.860 | 0.728 | 0.679 | 0.703 | 583 |
|  | Infiltration | 0.821 | 0.823 | 0.691 | 0.751 | 633 |
|  | Cardiopathy | 0.810 | 0.701 | 0.735 | 0.717 | 592 |
|  | Bilateral Hilar | 0.638 | 0.612 | 0.437 | 0.509 | 607 |
|  | Dyspnea | 0.596 | 0.710 | 0.533 | 0.609 | 597 |
|  | Apical Hypercarbia | 0.583 | 0.579 | 0.562 | 0.570 | 567 |
|  | Hypertrophy | 0.600 | 0.566 | 0.542 | 0.554 | 580 |
|  | Enlargement AP | 0.631 | 0.638 | 0.510 | 0.567 | 599 |
|  | Enlargement PA | 0.689 | 0.765 | 0.546 | 0.638 | 548 |
|  | Oval Opacity | 0.808 | 0.765 | 0.711 | 0.737 | 582 |
|  | Pleural Thickening | 0.769 | 0.674 | 0.685 | 0.679 | 556 |
|  | Mediastinal | 0.553 | 0.733 | 0.818 | 0.773 | 600 |
|  | Pulmonary Cavity | 0.776 | 0.634 | 0.660 | 0.647 | 595 |
|  | Fracture | 0.570 | 0.235 | 0.160 | 0.190 | 572 |
|  | Tuberculosis | 0.823 | 0.863 | 0.683 | 0.763 | 558 |

📑 Intra-language evaluation performance compared to ground truth
| Dataset | NLG Metrics |  NLG Metrics |  NLG Metrics |  NLG Metrics | CE Metrics | CE Metrics | CE Metrics |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  | BLEU-1 | BLEU-4 | ROUGE-L | METEOR | Precision | Recall | F-1 |
| CASIA-CXR | 0.404 | 0.177 | 0.341 | 0.158 | 0.705 | 0.630 | 0.665 |

📑 Cross-language evaluation using NLG and CE Metrics against English-language models
| Dataset | Model | NLG Metrics | NLG Metrics | NLG Metrics | NLG Metrics  | CE Metrics | CE Metrics | CE Metrics |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  | / | BLEU-1 | BLEU-4 | ROUGE-L | METEOR | Precision | Recall | F-1 |
| Open-i  | R2Gen  | 0.470 | 0.304 | 0.371 | 0.187 | / | / | / |
|  | CMCL  | 0.473 | 0.305 | 0.378 | 0.186 | / | / | / |
|  | PPKED  | 0.483 | 0.315 | 0.376 | 0.190 | / | / | / |
|  | CA  | 0.492 | 0.314 | 0.381 | 0.193 | / | / | / |
|  | AlignTR  | 0.484 | 0.313 | 0.379 | 0.204 | / | / | / |
|  | M2TR | 0.486 | 0.317 | 0.390 | 0.192 | / | / | / |
|  MIMIC-CXR | R2Gen  | 0.353 | 0.103 | 0.227 | 0.142 | 0.333 | 0.273 | 0.276 |
|  | CMCL | 0.334 | 0.097 | 0.281 | 0.133 | / | / | / |
| | PPKED | 0.36 | 0.106 | 0.284 | 0.149 | / | / | / |
|  | CA  | 0.35 | 0.109 | 0.283 | 0.151 | 0.352 | 0.298 | 0.303 |
|  | AlignTR | 0.378 | 0.112 | 0.283 | 0.158 | / | / | / |
|  | M2TR  | 0.378 | 0.107 | 0.272 | 0.145 | 0.240 | 0.428 | 0.308 |
| CASIA-CXR (Ours) | Ours | 0.357 | 0.197 | 0.314 | 0.177 | 0.340 | 0.437 | 0.384 |

## 📔 Figures
📑  Samples of our medical reports in French
![](https://metmer.net/CASIA-CXR/Img/SampleReports.png)
📑 The confusion matrix for disease classification performance
![](https://metmer.net/CASIA-CXR/Img/Matrix.jpg)
📑 Natural Language Generation (NLG) performance
![](https://metmer.net/CASIA-CXR/Img/Imgp.jpg)

## 📔 Contact
* #
