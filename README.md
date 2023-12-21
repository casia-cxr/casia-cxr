# An Open Dataset of Chest X-rays with Benchmarks on Automatic Radiology Report Generation in French

# Introduction
Medical report generation (MRG), which aims to automatically generate a textual description of a specific medical image (e.g., a chest X-ray), has recently received growing research interest. Building on the success of image captioning, medical report generation has become achievable. However, generating language-specific radiology reports presents is a challenge for datadriven models due to their reliance on paired image-report datasets, which are labor-intensive, time-consuming, and costly. In this paper, we introduce a new chest X-ray benchmark dataset, namely CASIA-CXR, consisting of high-resolution chest radiographs associated with medical reports originally written in French. To the best of our knowledge, this is the first public chest radiograph dataset with medical reports in this particular language. Importantly, we propose a simple yet effective multimodal encoder-decoder contextually-guided framework for medical report generation in French validated using our proposed dataset. We evaluate our framework using metrics from natural language generation and clinical efficacy, supplemented by human evaluations performed by radiologists. The dataset is freely available to advance a wide range of research in medical computer vision and natural language processing. It is available for download at: https://github.com/casiacxr/.

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
|  CASIA-CXR (ours) |       11,1K      |    11,1K      |      11,1K    |    CL/R         |        24        |         7,7K         | 3,3K |   /  |     JPEG     |      RIR/RP     |      French     |     2023     |


📄 Ablation Study

+----------------+----------------------------+---------------------------+
|      Our       |         CE Metrics         |        NLG Metrics        |
|      Model     |                            |                           |
+----------------+-----------+--------+-------+--------+--------+---------+
|                | Precision | Recall |   F1  | BLEU-1 | BLEU-4 | ROUGE-L |
+----------------+-----------+--------+-------+--------+--------+---------+
|    w/o D_Txt   |   0.650   |  0.550 | 0.561 |  0.300 |  0.140 |  0.280  |
+----------------+-----------+--------+-------+--------+--------+---------+
|   w/o D_Fused  |   0.620   |  0.520 | 0.540 |  0.290 |  0.130 |  0.260  |
+----------------+-----------+--------+-------+--------+--------+---------+
| w/o D_Enriched |   0.610   |  0.500 | 0.520 |  0.280 |  0.120 |  0.250  |
+----------------+-----------+--------+-------+--------+--------+---------+
|    Baseline    |   0.673   |  0.611 | 0.601 |  0.328 |  0.157 |  0.314  |
+----------------+-----------+--------+-------+--------+--------+---------+

📄 Model Performance
XXXXXXXXXX

📄 Classification Performance
|                 |       Disease      | Accuracy | Precision | Recall | F1-Score | Support |
|:---------------:|:------------------:|:--------:|:---------:|:------:|:--------:|:-------:|
| Global   Labels |    Cardiomegaly    |   0.830  |   0.937   |  0.825 |   0.875  |  3,756  |
|                 |    Pneumothorax    |   0.823  |   0.935   |  0.811 |   0.857  |  2,000  |
|                 |      Pneumonia     |   0.712  |   0.817   |  0.779 |   0.796  |  2,000  |
|                 |  Pleural Effusion  |   0.660  |   0.841   |  0.598 |   0.684  |  2,000  |
|                 |        Mass        |   0.582  |   0.692   |  0.630 |   0.659  |  1,355  |
|  Local   Labels |  Pulmonary Opacity |   0.580  |   0.373   |  0.460 |   0.410  |   680   |
|                 |      Emphysema     |   0.811  |   0.701   |  0.748 |   0.722  |   595   |
|                 |        Edema       |   0.602  |   0.655   |  0.482 |   0.554  |   609   |
|                 |     Atelectasis    |   0.715  |   0.722   |  0.701 |   0.750  |   554   |
|                 |     Lung Tumor     |   0.721  |   0.843   |  0.717 |   0.774  |   584   |
|                 |    Calcification   |   0.860  |   0.728   |  0.679 |   0.702  |   583   |
|                 |    Infiltration    |   0.821  |   0.823   |  0.691 |   0.750  |   633   |
|                 |     Cardiopathy    |   0.810  |   0.701   |  0.735 |   0.717  |   592   |
|                 |   Bilateral Hilar  |   0.638  |   0.612   |  0.437 |   0.508  |   607   |
|                 |       Dyspnea      |   0.596  |   0.710   |  0.533 |   0.609  |   597   |
|                 | Apical Hypercarbia |   0.583  |   0.579   |  0.562 |   0.568  |   567   |
|                 |     Hypertrophy    |   0.600  |   0.566   |  0.542 |   0.552  |   580   |
|                 |   Enlargement AP   |   0.631  |   0.638   |  0.510 |   0.565  |   599   |
|                 |   Enlargement PA   |   0.689  |   0.765   |  0.546 |   0.636  |   548   |
|                 |    Oval Opacity    |   0.808  |   0.765   |  0.711 |   0.738  |   582   |
|                 | Pleural Thickening |   0.769  |   0.674   |  0.685 |   0.679  |   556   |
|                 |     Mediastinal    |   0.553  |   0.733   |  0.818 |   0.771  |   600   |
|                 |  Pulmonary Cavity  |   0.776  |   0.634   |  0.660 |   0.646  |   595   |
|                 |      Fracture      |   0.570  |   0.235   |  0.160 |   0.190  |   572   |
|                 |    Tuberculosis    |   0.823  |   0.863   |  0.683 |   0.748  |   558   |

📄 XXXXXXXXXXXX
📄 Human Evaluation

|      Criteria     | Baseline | Variants | Variants |
|:-----------------:|:--------:|:--------:|:--------:|
|                   |          |   D_Txt  |  D_Fused |
| Comprehensiveness |    4.1   |    3.1   |    3.4   |
|      Fluency      |    4.1   |    3.0   |    3.1   |
|    Faithfulness   |    4.3   |    3.1   |    3.3   |
![](XXXXXXXXX)

