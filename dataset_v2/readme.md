## Toraman22 Hate Speech Dataset v2 

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


| F1-Score | Neutral | Offensive | Hateful | Weighted |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Bert-base-uncased (EN) | 0.968 ± 0.002 | 0.858 ± 0.008 | 0.631 ±  0.039 | 0.940 ± 0.004 |
| Bert-base-turkish-uncased (TR) | 0.946 ± 0.002 | 0.852 ± 0.005 | 0.887 ± 0.005 | 0.910 ± 0.003 |


Please cite the following paper.

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

