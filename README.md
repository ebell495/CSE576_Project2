# CSE576_Project2

Pretraining Colab Notebook: https://colab.research.google.com/drive/1XYdqwQoAqZPUa524reehwcOe-zcy93Zy?usp=sharing

Finetuning Colab Notebook: https://colab.research.google.com/drive/1dmb7WYaPWnsYVHtO37DsIQVKCNjAM2Q3?usp=sharing

Trained Models: https://drive.google.com/drive/folders/17r6JXdVbzpj9qE8ZPSu_XZQEl86N6_g_?usp=sharing

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
The finetuning domain is from 0-9999. The out of domain values are from 0-999999. We have pretrained 2 sets of models, one set up to the in domain range, and the other up to the out of domain range. We are interested in seeing if the out of domain results--predicting the number from numeration--performs better based on the pretraining techniques and ranges.


### In Domain


|         In Domain            | 0-9999  | 0-999999
|----------------------|:-:|:-:|
| T5-Base (Control)    | 89.223%  | -- |
| 1-Mask Numeration    |   |   |
| Many-Mask Numeration |  90.19% |   |
| 1-Mask Number        |   |   |
| Many-Mask Number     | 99.533%  |   |
| Mixed-Mask           | 99.599%  | 99.833%  |

### Out of Domain
These are the results of testing a pre-trained and fine tuned model on an out of domain range.

|         Out-Of-Domain             | 0-9999  | 0-999999
|----------------------|:-:|:-:|
| T5-Base (Control)    |  12.479% | --  |
| 1-Mask Numeration    |   |   |
| Many-Mask Numeration |  2.348% |   |
| 1-Mask Number        |   |   |
| Many-Mask Number     | 2.188%  |   |
| Mixed-Mask           |  2.405% |  4.117%  |
