# Secure Image Display on Object Detection
### Object-wise Secure Image Display Method for Screen Capture Protection   
(Scopus / IEIE Transactions on Smart Processing and Computing)

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
    
### Protection Zone Localization Algorithm (recurrsive)
    Input 𝛼 by Eq.(3) 𝑏1 ~ 𝑏𝑛  
    Output 𝛼 by 𝑝𝑓1 ~ 𝑝𝑓𝑛  
    
    function localization (𝛼, count)
        if (count reaches the end of 𝛼) return 𝛽
        create temporary protection zone 𝛽 as initial list of 𝛼`
        create 𝑝𝑐𝑜𝑢𝑛𝑡 in 𝛽 and copy 𝛼 [count]
        
        for (i increase from count + 1 to the end of 𝛼)
            if (overlapped with 𝑝𝑐𝑜𝑢𝑛𝑡 and 𝛼 [i])
                update 𝑝𝑐𝑜𝑢𝑛𝑡 by Eq.(1)
                𝛼 [i] is deleted
        count is incremented by 1
        localization (𝛼, count)
        
    while (overlapping)
        if (no more overlapping) return 𝛼
        localization(𝛼, count) updates 𝛼
    
### Figure
  ![3](https://user-images.githubusercontent.com/75716601/106891773-886e0400-672e-11eb-9fb4-7778a8786c4d.jpg)
