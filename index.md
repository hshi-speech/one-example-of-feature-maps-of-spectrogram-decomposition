## ICASSP 2022 -- Spectrogram Decomposition

The below are feature maps of baseline (CRN, only noisy input) and proposed spectrogram decomposition method. 


| :--: | :--: | :--: | :--: | :--: | :--: |  
| layer name | input size | hyperparam.  | output size | CRN (baseline) | composition (proposed) |  
|input layer |   n×257×F  |      -       |      -      |   noisy spec.  |   decomposed spec.     |  
|conv2d 1    | n×257×F    | 2×3,(1,2),16 | 16×128×F    |        -       |            -           |  
|conv2d 2    | 16×128×F   | 2×3,(1,2),32 | 32×63×F     |        -       |            -           |  
|conv2d 3    | 32×63×F    | 2×3,(1,2),64 | 64×31×F     |        -       |            -           |  
|conv2d 4    | 64×31×F    | 2×3,(1,2),128| 128×15×F    |        -       |            -           |  
|conv2d 5    | 128×15×F   | 2×3,(1,2),256| 256×7×F     |        -       |            -           |  
|reshape     | 256×7×F    | -            | F×1,792     |        -       |            -           |  
|lstm layer  | F×1,792    | 1,792        | F×1,792     |        -       |            -           |  
|lstm layer  | F×1,792    | 1,792        | F×1,792     |        -       |            -           |  
|reshape     | F×1,792    | -            | 256×7×F     |        -       |            -           |  
|deconv2d 5  | 512×7×F    | 2×3,(1,2),128| 128×15×F    |        -       |            -           |  
|deconv2d 4  | 256×15×F   | 2×3,(1,2),64 | 64×31×F     |        -       |            -           |  
|deconv2d 3  | 128×31×F   | 2×3,(1,2),32 | 32×63×F     |        -       |            -           |  
|deconv2d 2  | 64×63×F    | 2×3,(1,2),16 | 16×128×F    |        -       |            -           |  
|deconv2d 1  | 32×128×F   | 2×3,(1,2),1  | 1×257×F     |        -       |            -           |  


