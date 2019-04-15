# Readme
In this work, we focus on the experimental methodology used by two state-of-the-art methods, Badjatiya et al. [2], and Agrawal and Awekar [3].
We analyze the methodology implemented in these works and how they can be generalized to other datasets. The results of our research evidence methodological problems, and a relevant dataset bias. Consequently, performance claims of the current state-of-the-art have become overestimated. The issues that we have encountered are mostly due to the overfitting of data and sampling issues. We make an analysis of the implications for current research and reconducte experiments to give a more accurate idea of the current state-of-the art methods 

## Datasets
In this work we use three different datasets. We used the trainning English dataset of the SemEval 2019 Task5 [5]. Please download the dataset and unzip at Data/ from [here](https://goo.gl/forms/UPD2m8isvXMTvXV73) .

The second dataset is the one costructed by Wassem and Hovy [1], they made the tweets ID and labels public and we recovered the information using the Twitter API. 

A third dataset was constructed by us, using part of the Waseem and Hovy dataset, and part of the dataset described in Davidson et al. [4]. To get these datasets ready for use you have to run the following command:

```
$python Download_Data.py   -ct 'consumer_token' -cs 'consumer_secret' -at 'access_token' -ats 'access_token_secret'
```

Where consumer_token, consumer_secret, access_token and access_token_secret are the corresponding credentials to use the Twitter API.

## Word vectors
For these experiments we have also used embeddings for initialization. Please download and unzip the vectors at Vectors/ 

[Glove](https://nlp.stanford.edu/projects/glove/)


[Sentiment Specific word embeddings (SSWE)](http://ir.hit.edu.cn/~dytang/paper/sswe/embedding-results.zip) 


## Requirements
- Keras
- Theano
- Gensim
- xgboost
- NLTK
- Sklearn
- Numpy
- Keras
- Tflearn
- Tensorflow

<!-- 
## Description of the Experiments 
### Experiment 1
We reproduced the Agrawal and Awekar [3] and Badjatiya et al. [2] best reported models, following closely their paper description and the companion code.
### Experiment 2
In this experiment we take into account the issues we observed in the original implementation and modified the code consequently.
#### Agrawal and Awekar model
We re-conducted the same method proposed by Agrawal and Awekar [1] but this time making first the train-test splitting and then oversamplingthe train set before training the models. 
#### Badjatiya et al model
We re-run thesame method proposed by Badjatiya et al. [2] but this timeextracting features only from the set train (by using the LSTM-based architecture), then training the GBDT classifierwith these features over the same set train, and reporting all the metrics over the ttest.
### Experiment 3
To estimate how well do these models generalize to other dataset from the same domain, evaluate those models –generated on the complete Waseem & Hovy dataset on the SemEval2019 dataset.
### Experiment 4
We partitioned the Wassem & Hovy dataset into trainning and testing sets, ensuring that no user is repeated between train and test set, and also ensuring at least an 85% of tweets of each class are in the train set. 
To run the Experiment for one and other method you can run:
### Experiment 5
In this experiment we perform a 10-fold cross validation considering partitions with no overlapping users between the train and test sets using the enriched dataset.
### Experiment 6
To corroborate the generalization of the resulting model we use our newly created dataset to train the modelsproposed by Badjatiya et al. [2] and by Agrawal and Awekar[1]. Then we evaluate these models on previously unseen data by classifying tweets in the SemEval 2019 set. -->

## Instructions to run
After running the previous command and download an unzip the SemEval dataset, you will be able to run the experiments running the following command:
```
$python ModelX_Experiments/Experiment_X.py
```
For example, to run the Experiment 1 with the models of Badjatiya et al. you have to run:
```
$python Model1_Experiments/Experiment_1.py
```
To run the Experiment 1 with the models of Agrawal and Awekar you have to run:
```
$python Model2_Experiments/Experiment_1.py
```
### References

[1] Z. Waseem, D. Hovy _Hateful Symbols or Hateful People\? Predictive Features for Hate Speech on Detection on Twitter_
```                    
@inproceedings{DBLP:conf/naacl/HeeaseemH16,
  author    = {Zeerak Waseem and
               Dirk Hovy},
  title     = {Hateful Symbols or Hateful People? Predictive Features for Hate Speech
               Detection on Twitter},
  booktitle = {Proceedings of the Student Research Workshop, SRW@HLT-NAACL 2016,
               The 2016 Conference of the North American Chapter of the Association
               for Computational Linguistics: Human Language Technologies, San Diego
               California, USA, June 12-17, 2016},
  url       = {http://aclweb.org/anthology/N/N16/N16-2013.pdf},
}
```
[2]  P. Badjatiya, S. Gupta, M. Gupta, V. Varma _Deep learning for hate speech detection in tweets_
```
@inproceedings{badjatiya2017deep,
  title={Deep learning for hate speech detection in tweets},
  author={Badjatiya, Pinkesh and Gupta, Shashank and Gupta, Manish and Varma, Vasudeva},
  booktitle={Proceedings of the 26th International Conference on World Wide Web Companion},
}
```
[3] S. Agrawal, A. Awekar _Deep learning for detecting cyberbullying across multiple social media platforms_
```
@inproceedings{DBLP:conf/ecir/AgrawalA18,
  author    = {Sweta Agrawal and
               Amit Awekar},
  title     = {Deep Learning for Detecting Cyberbullying Across Multiple Social Media
               Platforms},
  booktitle = {Advances in Information Retrieval - 40th European Conference on {IR}
               Research, {ECIR} 2018, Grenoble, France, March 26-29, 2018, Proceedings},
  url       = {https://doi.org/10.1007/978-3-319-76941-7_11},
 }
```
[4] T. Davidson, D. Warmsley, W. Macy, I.Weber _Automated Hate Speech Detection and the Problem of Offensive Language_
```
@inproceedings{davidson2017automated,
	author    = {Thomas Davidson and 	Dana Warmsley and Michael W. Macy and	Ingmar Weber},
	title     = {Automated Hate Speech Detection and the Problem of Offensive Language},
	booktitle = {Proceedings of the Eleventh International Conference on Web and Social
	url       = {https://aaai.org/ocs/index.php/ICWSM/ICWSM17/paper/view/15665},
	}
```
[5] V. Valerio, C. Bosco, V. Patti, I.Weber, M. Sanguinetti, E. Fersini, D.Nozza, F.Rangel, P. Rosso _Shared Task on Multilingual Detection of Hate_
```
@misc{SemEval19,
  author = {Valerio Basile and Cristina Bosco and  Viviana Patti and  Manuela Sanguinetti and  Elisabetta Fersini and  Debora Nozza and   Francisco Rangel and  Paolo Rosso},
  title = {Shared Task on Multilingual Detection of Hate},
  howpublished = {SemEval 2019, Task 5, \url{https://competitions.codalab.org/competitions/19935}}
}
```