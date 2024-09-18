# Update on September 18th, 2024:
We publish all dataset contents in this repo. We also publish ~20k image files associated with the tweets.

# Published Models:
English hate speech detection model finetuned on Dataset v2:

https://huggingface.co/ctoraman/hate-speech-bert

Turkish hate speech detection model finetuned on Dataset v2:

https://huggingface.co/ctoraman/hate-speech-berturk

# Large-Scale Hate Speech Datasets
This repository contains the utilized dataset in the LREC 2022 paper "Large-Scale Hate Speech Detection with Cross-Domain Transfer". This study mainly focuses hate speech detection in Turkish and English. In addition, domain transfer success between hate domains is also examined.

There are two dataset versions. 

**Dataset v1:** The original dataset that includes **100,000 tweets per English and Turkish**, published in [LREC 2022](https://aclanthology.org/2022.lrec-1.238/). The annotations with **more than 60% agreement** are included.

**Dataset v2:** A more reliable dataset version that includes **68,597 tweets for English and 60,310 for Turkish**. The annotations with **more than 80% agreement** are included.

## Toraman22 Hate Speech Detection Dataset v2 

We acknowledge that some annotations in the original dataset (v1) are controversial. Therefore, we publish a more reliable dataset version (v2) that includes only the tweets with more than 80% annotator agreement. The dataset v2 has 128,907 tweets. 60,310 of them are Turkish, and 68,597 are English. Explanations of the columns of the file are as follows:

tweet_id

user_id	

user_name	

screen_name

verified: If user's profile is verified.	

created_at: The date that user's profile is created.	

friends_count: User's total number of followees	

followers_count: User's total number of followers	

statuses_count: User's total number of sharings	

favourites_count: User's total number of likes	

default_piclabel: User's profile picture	

topic: Religion (0), Gender (1), Race (2), Politics (3), or Sports (4)

language: Turkish (0) or English (1)	

date: Tweet's published date	

text: Tweet's text contents

label_0: How many times tweet is labeled Normal (0)

label_1: How many times tweet is labeled Offensive (1)

label_2: How many times tweet is labeled Hate (2)	

label_score: Final annotation label


Distibution of tweets in the dataset is as follows:

| Lang. | Domain | Hate | Offensive | Normal | Total |
|----------|----------|----------|----------|----------|----------|
| EN | Religion<br>Gender<br>Race<br>Politics<br>Sport <br>  **Total**| 328<br>255<br>405<br>343<br>286 <br> **1,617 (2%)**| 2,369<br>3,043<br>1,631<br>2,972<br>2,814 <br> **12,829 (19%)** | 10,713<br>9,537<br>12,566<br>9,994<br>11,341 <br> **54,151 (79%)** | 13,410<br>12,835<br>14,602<br>13,309<br>14,441 <br> **68,597**
| TR | Religion<br>Gender<br>Race<br>Politics<br>Sport <br> **Total**| 2,281<br>970<br>1,897<br>3,657<br>4,016 <br> **12,821 (21%)**| 3,814<br>3,385<br>2,276<br>1,529<br>3,930 <br>  **14,934 (25%)** | 5,058<br>8,353<br>8,236<br>6,251<br>4,657 <br> **32,555 (54%)**| 11,153<br>12,708<br>12,409<br>11,437<br>12,603 <br> **60,310**

Using the dataset v2, we run BERT and BERTurk by applying 10-fold cross validation ([as in the published version, v1](https://aclanthology.org/2022.lrec-1.238/)). Each data split has 90% of train and 10% of test. We report the average F1 scores.

| F1-Score | Neutral | Offensive | Hateful | Weighted |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Bert-base-uncased (EN) | 0.968 ± 0.002 | 0.858 ± 0.008 | 0.631 ±  0.039 | 0.940 ± 0.004 |
| Bert-base-turkish-uncased (TR) | 0.946 ± 0.002 | 0.852 ± 0.005 | 0.887 ± 0.005 | 0.910 ± 0.003 |

Thanks to **Izzet Emre Kucukkaya** for helping in the preparation of the dataset v2.

## Toraman22 Hate Speech Detection Dataset v1

The dataset is composed of 200,000 tweets. Half of them is Turkish and other half is English. We also have domain information of the hate speech. These domains are Religion, Gender, Race, Politics, Sports. Each domain has 20,000 tweets in each respective language. 5 hate annotations of the tweet are also given. Since we followed Twitter's Terms and Conditions, publish tweet IDs not the tweet content directly. Explanations of the columns of the file are as follows:

tweet_id

user_id	

user_name	

screen_name

verified: If user's profile is verified.	

created_at: The date that user's profile is created.	

friends_count: User's total number of followees	

followers_count: User's total number of followers	

statuses_count: User's total number of sharings	

favourites_count: User's total number of likes	

default_piclabel: User's profile picture	

topic: Religion (0), Gender (1), Race (2), Politics (3), or Sports (4)

language: Turkish (0) or English (1)	

date: Tweet's published date	

text: Tweet's text contents

label_0: How many times tweet is labeled Normal (0)

label_1: How many times tweet is labeled Offensive (1)

label_2: How many times tweet is labeled Hate (2)	

label_score: Final annotation label

Distibution of tweets in the dataset is as follows:

| Lang. | Domain | Hate | Offensive | Normal | Total |
|----------|----------|----------|----------|----------|----------|
| EN | Religion<br>Gender<br>Race<br>Politics<br>Sport <br> **Total** | 1,427<br>1,313<br>1,541<br>1,610<br>1,434 <br> **7,325 (7%)** | 5,221<br>6,431<br>3,846<br>6,018<br>5,624<br> **27,140 (27%)** | 13,352<br>12,256<br>14,613<br>12,372<br>12,942 <br> **65,535 (66%)**| 20,000<br>20,000<br>20,000<br>20,000<br>20,000 <br> **100,000**
| TR | Religion<br>Gender<br>Race<br>Politics<br>Sport <br> **Total**| 5,688<br>2,780<br>5,095<br>7,657<br>6,373<br> **27,593 (28%)** | 7,435<br>6,521<br>4,905<br>4,253<br>7,633<br> **30,747 (31%)**| 6,877<br>10,699<br>10,000<br>8,090<br>5,994<br> **41,660 (41%)**| 20,000<br>20,000<br>20,000<br>20,000<br>20,000 <br> **100,000**

## Contact
Please contact Cagri Toraman (cagritoraman@gmail.com) in case of any issues with the datasets. 

## Citation
If you make use of this dataset, please cite following paper.

```bibtex
@InProceedings{toraman2022large,
  author    = {Toraman, Cagri  and  \c{S}ahinu\c{c}, Furkan and Yilmaz, Eyup Halit},
  title     = {Large-Scale Hate Speech Detection with Cross-Domain Transfer},
  booktitle = {Proceedings of the Language Resources and Evaluation Conference},
  month     = {June},
  year      = {2022},
  address   = {Marseille, France},
  publisher = {European Language Resources Association},
  pages     = {2215--2225},
  url       = {https://aclanthology.org/2022.lrec-1.238}
}

```
