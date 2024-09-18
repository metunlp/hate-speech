# Toraman22 Hate Speech Dataset v1

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
