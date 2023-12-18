# An Open Dataset of Chest X-rays with Benchmarks on Automatic Radiology Report Generation in French

# Introduction
Medical report generation (MRG), which aims to automatically generate a textual description of a specific medical image (e.g., a chest X-ray), has recently received growing research interest. Building on the success of image captioning, medical report generation has become achievable. However, generating language-specific radiology reports presents a key hurdle for data-driven models due to their reliance on paired image-report datasets, which are labor-intensive, time-consuming, and costly. In this paper, we introduce a new chest X-ray benchmark dataset, namely \textit{CASIA-CXR}, consisting of high-resolution chest radiographs associated with medical reports originally written in French. To the best of our knowledge, this is the first public chest radiograph dataset with medical reports in this particular language. Importantly, we propose a simple yet effective multimodal encoder-decoder contextually clinical-guided framework for medical report generation in French validated using our proposed dataset. We evaluate the performance of our framework using metrics from natural language generation and clinical efficacy, in addition to human evaluations performed by radiologists. The dataset is freely available to advance a wide range of research in medical computer vision and natural language processing. It is available for download at: https://github.com/casia-cxr/.

# Website
XXXXXXXX

📄 XXXXXXXXXXXX
|      Dataset      | Patients Number | Studies Number | Images Number | Annotation Type | Annotated Labels | PA View | AP View  | L View    | Image Format | Labeling Method | Report Language | Release Year |
|:-----------------:|:---------------:|:--------------:|:-------------:|:---------------:|:----------------:|:--------------------:|:----:|:----:|:------------:|:---------------:|:---------------:|:------------:|
| Shenzhen Hospital |        /        |        /       |      340      |        Cl       |         2        |          340         |   /  |   /  |     DICOM    |        RI       |     English     |     2014     |
|      IU X-ray     |       3,9K      |      3,9K      |      7,4K     |        R        |         /        |         3,9K         |   /  | 3,9K |     JPEG     |        RI       |     English     |     2016     |
|   Chest X-ray 14  |       31K       |        /       |      112K     |     CL / BB     |        14        |          67K         |  45K |   /  |      PNG     |      RP/RI      |     English     |     2017     |
|       CX-CHR      |       35K       |       35K      |      45K      |        CL       |        155       |           /          |   /  |   /  |     JPEG     |        RP       |     Chinese     |     2018     |
|      CheXpert     |       65K       |      188K      |      224K     |        CL       |        14        |          29K         | 162K |  32K |     JPEG     |      RCI/RP     |     English     |     2019     |
|     MIMIC-CXR     |       65K       |      224K      |      372K     |       CL/R      |        14        |         130K         | 162K | 122k |     DICOM    |        RP       |     English     |     2019     |
|      PadChest     |       67K       |      110k      |      160k     |       CL/R      |        193       |          96K         |  20K |  51K |     DICOM    |      RIR/RP     |     Spanish     |     2019     |
|     VinDR-CXR     |        /        |        /       |      100k     |      CL/BB      |        28        |          18K         |   /  |   /  |     DICOM    |        RI       |     English     |     2020     |
|       BIMCV       |       1,3K      |      2,3K      |      3,2K     |        CL       |         2        |         1,1K         | 1,3K |  815 |     DICOM    |        LT       |     English     |     2020     |
|  CXR14 Rad-Labels |       1,7K      |        /       |      4,3K     |        CL       |         4        |         3,2K         | 1,1K |   /  |     JPEG     |       RCI       |     English     |     2020     |
|  CASIA-CXR (ours) |       5,5K      |      5,5K      |      5,5K     |       CL/R      |        21        |         4,5K         |  947 |   /  |     JPEG     |      RIR/RP     |      French     |     2023     |



📄 Human Evaluation

|      Criteria     | Baseline | Variants | Variants |
|:-----------------:|:--------:|:--------:|:--------:|
|                   |          |   D_Txt  |  D_Fused |
| Comprehensiveness |    4.1   |    3.1   |    3.4   |
|      Fluency      |    4.1   |    3.0   |    3.1   |
|    Faithfulness   |    4.3   |    3.1   |    3.3   |
![](XXXXXXXXX)

📄 Ablation Study

|  Our Model  | BLEU-1 | BLEU-4 | ROUGE-L |
|:-----------:|:------:|:------:|:-------:|
|  w/o D_Txt  |  0.290 |  0.111 |  0.201  |
| w/o D_Fused |  0.345 |  0.144 |  0.281  |
|   Baseline  |  0.404 |  0.177 |  0.341  |
![](XXXXXXXXX)

📄 Model Performance
|  Dataset  | Model | NLG metrics |        |        |        |       |       | Clinical Efficacy metrics |           |        |           |
|:---------:|:-----:|:-----------:|:------:|:------:|:------:|:-----:|:-----:|:-------------------------:|:---------:|:------:|:---------:|
|           |       |    BLEU-1   | BLEU-2 | BLEU-3 | BLEU-4 | CIDer | Rouge |          Accuracy         | Precision | Recall | F-1 Score |
| CASIA-CXR |  Ours |    0.404    |  0.297 |  0.212 |  0.127 | 0.201 | 0.341 |           0.712           |   0.705   |  0.630 |   0.660   |
![](XXXXXXXXX)

📄 Classification Performance
|                                      |       Disease      |    Accuracy    |    Precision   | Recall   |    F1-Score    |   Support  |
|:------------------------------------:|:------------------:|:--------------:|:--------------:|:--------:|:--------------:|:----------:|
|              Global  Labels          |    Cardiomegaly    |      0.814     |      0.919     |   0.809  |      0.858     |    1313    |
|                                      |    Pneumothorax    |      0.807     |      0.917     |   0.795  |      0.840     |     700    |
|                                      |      Pneumonia     |      0.698     |      0.801     |   0.764  |      0.780     |     700    |
|                                      |  Pleural Effusion  |      0.647     |      0.825     |   0.586  |      0.671     |     700    |
|                                      |        Mass        |      0.571     |      0.678     |   0.618  |      0.646     |     467    |
|                         Local Labels |  Pulmonary Opacity |      0.580     |      0.373     |   0.460  |      0.410     |     680    |
|                                      |      Emphysema     |      0.795     |      0.687     |   0.733  |      0.708     |     220    |
|                                      |        Edema       |      0.590     |      0.642     |   0.473  |      0.543     |     88     |
|                                      |     Atelectasis    |      0.895     |      0.977     |   0.897  |      0.934     |     210    |
|                                      |     Lung Tumor     |      0.707     |      0.826     |   0.703  |      0.759     |     410    |
|                                      |    Calcification   |      0.843     |      0.714     |   0.666  |      0.688     |     115    |
|                                      |    Infiltration    |      0.805     |      0.807     |   0.677  |      0.735     |     77     |
|                                      |     Cardiopathy    |      0.794     |      0.687     |   0.721  |      0.703     |     180    |
|                                      |   Bilateral Hilar  |      0.625     |      0.600     |   0.428  |      0.498     |     80     |
|                                      |       Dyspnea      |      0.584     |      0.696     |   0.523  |      0.597     |     178    |
|                                      | Apical Hypercarbia |      0.572     |      0.568     |   0.551  |      0.557     |     199    |
|                                      |     Hypertrophy    |      0.588     |      0.555     |   0.531  |      0.541     |     102    |
|                                      |   Enlargement AP   |      0.619     |      0.625     |   0.500  |      0.554     |     210    |
|                                      |   Enlargement PA   |      0.675     |      0.750     |   0.535  |      0.624     |     222    |
|                                      |    Oval Opacity    |      0.792     |      0.750     |   0.697  |      0.724     |     111    |
|                                      | Pleural Thickening |      0.754     |      0.661     |   0.672  |      0.666     |     159    |
|                                      |     Mediastinal    |      0.786     |      0.719     |   0.802  |      0.756     |     229    |
|                                      |  Pulmonary Cavity  |      0.761     |      0.622     |   0.647  |      0.633     |     159    |
|                                      |      Fracture      |      0.559     |      0.230     |   0.157  |      0.186     |     59     |
|                                      |    Tuberculosis    |      0.807     |      0.846     |   0.670  |      0.733     |     192    |
|                                      |     No Findings    |      0.860     |      0.862     |   0.816  |      0.837     |    1230    |
![](XXXXXXXXX)

📄 Dataset Characteristics
|                    | Characteristics              | Training set |        | Testing set  |        |
|--------------------|------------------------------|--------------|--------|--------------|--------|
| Dataset Statistics | Years                        | 2019 to 2022 |        | 2019 to 2022 |        |
|                    | Number of scans              | 3,880        |        | 1,664        |        |
|                    | Number of annotators         | 5            |        | 5            |        |
|                    | Image Size                   | 2,372x3,000  |        | 2,372x3,000  |        |
|                    | Image Resized                | 512x512      |        | 512x512      |        |
|                    | Age (min, max)               | 40,90        |        | 40,90        |        |
|                    | Male                         | 2,546        |        | 1,091        |        |
|                    | Female                       | 1,327        |        | 568          |        |
|                    | Data Size(GB) Data Resized   | 8 GB 2.5 GB  |        | 2.5 GB 1 GB  |        |
| Local  Labels      | 1.     Pulmonary Opacity (%) | 680          | 17.52% | 250          | 15.02% |
|                    | 2.     Emphysema (%)         | 220          | 5.67%  | 57           | 3.42%  |
|                    | 3.     Edema (%)             | 88           | 2.26%  | 90           | 5.40%  |
|                    | 4.     Atelectasis (%)       | 210          | 5.41%  | 77           | 4.62%  |
|                    | 5.     Lung Tumor (%)        | 410          | 10.56% | 100          | 6.00%  |
|                    | 6.     Calcification (%)     | 115          | 2.96%  | 68           | 4.08%  |
|                    | 7.     Infiltration (%)      | 77           | 1.98%  | 33           | 1.98%  |
|                    | 8.     Cardiopathy (%)       | 180          | 4.63%  | 120          | 7.21%  |
|                    | 9.     Bilateral Hilar (%)   | 80           | 2.06%  | 73           | 4.38%  |
|                    | 10.   Dyspnea (%)            | 178          | 4.58%  | 99           | 5.94%  |
|                    | 11.   Apical Hypercarbia (%) | 199          | 5.12%  | 88           | 5.28%  |
|                    | 12.   Hypertrophy (%)        | 102          | 2.62%  | 93           | 5.58%  |
|                    | 13.   Enlargement AP (%)     | 210          | 5.41%  | 99           | 5.94%  |
|                    | 14.   Enlargement PA (%)     | 222          | 5.72%  | 89           | 5.34%  |
|                    | 15.   Oval Opacity (%)       | 111          | 2.86%  | 66           | 3.96%  |
|                    | 16.   Pleural Thickening (%) | 159          | 4.09%  | 31           | 1.86%  |
|                    | 17.   Mediastinal (%)        | 229          | 5.90%  | 79           | 4.74%  |
|                    | 18.   Lung Cavity (%)        | 159          | 4.09%  | 69           | 4.14%  |
|                    | 19.   Fracture (%)           | 59           | 1.52%  | 28           | 1.68%  |
|                    | 20.   Tuberculosis (%)       | 192          | 4.94%  | 55           | 3.30%  |
|                    | 21.   No Findings (%)        | 1230         | 31.70% | 541          | 32.51% |
| Global  Labels     | 1.     Cardiomegaly (%)      | 1313         | 33.84% | 564          | 33.89% |
|                    | 2.     Pneumothorax (%)      | 700          | 18.04% | 300          | 18.02% |
|                    | 3.     Pleural Effusion (%)  | 700          | 18.04% | 300          | 18.02% |
|                    | 4.     Pneumonia (%)         | 700          | 18.04% | 300          | 18.02% |
|                    | 5.     Mass (%)              | 467          | 12.03% | 200          | 12.01% |
