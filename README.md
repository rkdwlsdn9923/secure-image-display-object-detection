# Secure Image Display on Object Detection
### Object-wise Secure Image Display Method for Screen Capture Protection
  Protection Zone examples 1#  
  ![1](https://user-images.githubusercontent.com/75716601/106891718-712f1680-672e-11eb-8f50-94b91d920ee3.jpg)
                          examples 2#  
  ![2](https://user-images.githubusercontent.com/75716601/106891772-86a44080-672e-11eb-91c6-f007652cc494.jpg)

### Absorption bounding box Algorithm
     1: Input α by Eq.(2)
     2: Output α`
     3: step = 0
     4: while (true)
     5:     if (step is equal to the length of α) return
     6:     target = α[step]
     7:     for i = 0 to the length of α
     8:         if (target ≠ α[i])
     9:             D_a = target, D_b = α[i]
    10:             (x_1, y_1) = max value each top-left of D_a and D_b
    11:             (x_2, y_2) = min value each bottom-right of D_a and D_b
    12:             make width, height on coordinate (x_1, y_1), (x_2, y_2)
    13:             if not (width ≤ 0) or (height ≤ 0)
    14:                 The D_n` is initialized
    15:                 top-left (x, y) of D_n` = min value each top-left of D_a and D_b
    16:                 bottom-right (x, y) of D_n` = max value each bottom-right of D_a and D_b
    17:                 α[step] = D_n`
    18:                 α[i] is initialized
    19:                 step = step – 1
    20:                 break
    21:     step = step + 1

### Figure
  ![3](https://user-images.githubusercontent.com/75716601/106891773-886e0400-672e-11eb-9fb4-7778a8786c4d.jpg)
