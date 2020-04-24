# bt5153-applied-ml-hugs-for-bugs
This is the repository of codes used in NUS BT5153 final project "Auto-Streaming of MBS Customer Feedback" by Team Hugs for Bugs.

<p align="center">
  <img src="https://www.comp.nus.edu.sg/~pravein/soclogo.jpg" width="200">
</p>

The objective of this project is to achieve auto-streaming of customers' feedback to related departments for Marina Bay Sands ("MBS") Hotel. The original data is on [booking.com](https://www.booking.com/reviews/sg/hotel/marina-bay-sands.en-gb.html?aid=357004;label=gog235jc-1FCA0oyQE4qAZIM1gDaMkBiAEBmAEJuAEXyAEU2AEB6AEB-AEMiAIBqAIDuALg3vvxBcACAQ;sid=8a6dd48ab3f6c651d2176995dfe97040;customer_type=total;hp_nav=0;old_page=0;order=featuredreviews;page=4;r_lang=en;rows=75&). For our analysis, only "Cons", or negative comments, were taken into consideration. Data was then obtained using **web scraping** method by Python Beautifulsoups package.

For **data cleaning**, the texts were converted into lower-case. Punctuations, non-alphabetic characters were removed. Tokenization, stopword removal, word stemming were then performed.

Our data exploration consists of a few parts. First, a **word cloud** was generated to spot the most frequent words that appeared in the negative comments. Second, using the **topic modelling** techniques, we discovered the 4 most important topics. Lastly, **PyTextRank** was implemented to extract the top-ranked phrases.

As some positive comments were also found in cons, a **sentiment analysis** was then conducted to tell the desired comments from the false positive ones.

The last part is to feed the data into **machine learning** models. The outputs of the models are 8 columns of binary values, correponding to 8 departments identified. The target value, or department column, in the training dataset were pre-labelled manually. Models explored in this project include logistics regression, multinomial naive bayes, random forest, support vector machines, k-nearest neighbors and a simple neural network.

The steps are listed below:
1. [data scraping](/0.%20auto-streaming%20mbs%20feedback/1.%20data%20scraping)
2. [data cleaning](/0.%20auto-streaming%20mbs%20feedback/2.%20data%20cleaning)
3. [data exploration](/0.%20auto-streaming%20mbs%20feedback/3.%20data%20exploration)
4. [sentiment analysis](/0.%20auto-streaming%20mbs%20feedback/4.%20sentiment%20analysis)
5. [models](/0.%20auto-streaming%20mbs%20feedback/5.%20models)

There are 4 data files used:
- MBS_data.csv is the scraped data from the review site.
- cons_data.xlsx is the resultant file after sentence splitting and manual labeling were performed. It was also used as the input file for sentiment analysis.
- cons_data_full.xlsx is the file after removing all positive comments from cons_data.xlsx.
- data_cleaned.csv is the cleaned dataset and was used as the input file for model training.
