# CSE576_Project2

Colab Notebook: https://colab.research.google.com/drive/1XYdqwQoAqZPUa524reehwcOe-zcy93Zy?usp=sharing

## Masking Methodologies

- 1-Mask Numeration
   - This will randomly mask one of the words in the numeration.
   - One hundred twenty-three -> One \<mask> twenty-three
- Many-Mask Numeration
  - This will randomly mask one or more of the words in the numeration.
  - Three thousand four hundred fifty-five -> \<mask> thousand \<mask> \<mask> fifty-five
- 1-Mask Number
  - This will randomly mask one digit in the number
  - 4738 -> 4\<mask>738
- Many-Mask Number
  - This will random mask one or more digits in the number
  - 56483 -> 5\<mask>\<mask>83 or 5\<mask>4\<mask>3
- Mixed-Mask
  - This will randomly mask one or more digits in the number then mask the complement in the numeration
  - Three thousand four hundred fifty-five is the number 3455 -> \<mask> \<mask> four hundred fifty-\<mask> is the number 3\<mask>5\<mask>

## Results

### Out of Domain
These are the results of testing a pre-trained and fine tuned model on an out of domain range. This range is from the top of the trained range to 100 times that. For example, 0-100 would be tested on 100-10000

|         Out-Of-Domain             | 0-100  | 0-1000  |  0-100000 
|----------------------|---|---|---|
| T5-Base (Control)    |   |   |   |
| 1-Mask Numeration    |   |   |   | 
| Many-Mask Numeration |   |   |   |   
| 1-Mask Number        |   |   |   |   
| Many-Mask Number     |   |   |   |   
| Mixed-Mask           |   |   |   |   
