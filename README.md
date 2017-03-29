# cse6250-final-project

Proposal Report: [overleaf link](https://www.overleaf.com/8371794wnkynjkydwsn)

### Environment Setup
1. conda env create -f environment.yml
1. jupyter toree install --user --spark_home=<complete path>/spark-2.1.0-bin-hadoop2.7 --interpreters=PySpark
    1. If you experience error in running the PySpark kernel. Make sure you put "complete path", not relative path.
    1. If toree is not yet installed (should be included in environment.yml), run the ff. command:
        1. pip install https://dist.apache.org/repos/dist/dev/incubator/toree/0.2.0/snapshots/dev1/toree-pip/toree-0.2.0.dev1.tar.gz
        1. [github link](https://github.com/apache/incubator-toree)
1. extract the ff. data to code/data:
    1. DIAGNOSES_ICD.csv
    1. NOTEEVENTS.csv - a cleaned and sample version can be downloaded [here](https://drive.google.com/open?id=0B7IQxoKP3KPGWmFiUGlNTTBuWXM)
    1. DATA_TFIDF_HADM_TOP10.csv - tfidf data based on hadm_id<->top10 icd9codes [download link](https://drive.google.com/open?id=0B7IQxoKP3KPGWmFiUGlNTTBuWXM)
1. jupyter notebook
    1. Console command to run the notebook. Don't forget to set the kernel to "Toree Pyspark".

### Folder Structure
* code: all source code
    * data (you should download and extract the following here)
        * DIAGNOSES_ICD.csv
        * NOTEEVENTS.csv
        * PATIENTS.csv (will probably not use this)
* literature: important papers (pretty much the same w/ what is on slack)
* proposal: other proposal related documents

### Todo List
1. Data Preprocessing
    1. ~~top 10 all~~
    1. top 50 all (code ready)
    1. top 10 category
    1. top 50 category
    1. consider doing advance test and train split
        * maintain the test-train ratio of each category instead of just the test-train ratio of the whole dataset
1. Feature Selection
    1. bag of words
        * consider removing "very frequent words / stop words of the medical field" (Cesar's suggestion) 
    1. word2vec
1. Model Training and Testing
    1. Logistic Regression
        * implemented using spark.ml instead of spark.mllib. [reason in this link](http://stackoverflow.com/questions/30231840/difference-between-org-apache-spark-ml-classification-and-org-apache-spark-mllib)
    1. Random Forest
    1. Feed Forward NN
    1. RNN
    1. LSTM
    1. GRU
