## ICASSP 2022 -- Spectrogram Decomposition

The below are one sample of feature maps in baseline (CRN, only noisy input) and proposed spectrogram decomposition method. 


| :--: | :--: | :--: | :--: | :--: | :--: |  
| layer name | input size | hyperparam.  | output size | CRN (baseline) | composition (proposed) |  
|input layer |   n×257×F  |      -       |      -      |   noisy spec.  |   decomposed spec.     |  
|conv2d 1    | n×257×F    | 2×3,(1,2),16 | 16×128×F    | [feature maps](pics/baseline_conv1_p232_092.png) | [feature maps](pics/decomposition_conv1_p232_092.png) |  
|conv2d 2    | 16×128×F   | 2×3,(1,2),32 | 32×63×F     | [feature maps](pics/baseline_conv2_p232_092.png) | [feature maps](pics/decomposition_conv2_p232_092.png) |  
|conv2d 3    | 32×63×F    | 2×3,(1,2),64 | 64×31×F     | [feature maps](pics/baseline_conv3_p232_092.png) | [feature maps](pics/decomposition_conv3_p232_092.png) |  
|conv2d 4    | 64×31×F    | 2×3,(1,2),128| 128×15×F    | [feature maps](pics/baseline_conv4_p232_092.png) | [feature maps](pics/decomposition_conv4_p232_092.png) |  
|conv2d 5    | 128×15×F   | 2×3,(1,2),256| 256×7×F     | [feature maps](pics/baseline_conv5_p232_092.png) | [feature maps](pics/decomposition_conv5_p232_092.png) |  
|reshape     | 256×7×F    | -            | F×1,792     |        -       |            -           |  
|lstm layer  | F×1,792    | 1,792        | F×1,792     |        -       |            -           |  
|lstm layer  | F×1,792    | 1,792        | F×1,792     |        -       |            -           |  
|reshape     | F×1,792    | -            | 256×7×F     |        -       |            -           |  
|deconv2d 5  | 512×7×F    | 2×3,(1,2),128| 128×15×F    | [feature maps](pics/baseline_de1_p232_092.png) | [feature maps](pics/decomposition_de1_p232_092.png) |  
|deconv2d 4  | 256×15×F   | 2×3,(1,2),64 | 64×31×F     | [feature maps](pics/baseline_de2_p232_092.png) | [feature maps](pics/decomposition_de2_p232_092.png) |  
|deconv2d 3  | 128×31×F   | 2×3,(1,2),32 | 32×63×F     | [feature maps](pics/baseline_de3_p232_092.png) | [feature maps](pics/decomposition_de3_p232_092.png) |  
|deconv2d 2  | 64×63×F    | 2×3,(1,2),16 | 16×128×F    | [feature maps](pics/baseline_de4_p232_092.png) | [feature maps](pics/decomposition_de4_p232_092.png) |  
|deconv2d 1 (mask)  | 32×128×F   | 2×3,(1,2),1  | 1×257×F     | [feature maps](pics/baseline_de5_p232_092.png) | [feature maps](pics/decomposition_de5_p232_092.png) |  


