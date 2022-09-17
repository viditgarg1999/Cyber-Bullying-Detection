# Cyber-Bullying-Detection


In this project we have built a system in which we can extract the comments from any post on facebook and detect the cyber bullying by doing sentiment analysis. This system will segregrate the comments as positive, negative, abusive, neutral, facts, etc. The heart of this model is that we have mapped the comments of the user with reactions given by same user to make the model more precise. <br/>
This can be explained by an example, suppose a person posts a photo and some of his/her friend posts an abusive comments but along with a ‘love’ react on the post then that particular comment will not be considered as abusive or insulting because the friend have posted the comment with good intention. <br/>
Furthermore, this model is also compatible of translating the given text in any language into English and then doing the Sentiment Analysis.<br/>
Then we have visualized the results in an interactive manner such that even a naive user can understand the exact statistics.  




# Methodology  
  <br/><br/>
**Datasets Used**  
  
We have created a corpus of common negative phrases, words and facts, using the Selenium library to scrape the web and extract them.  
  
For training, we have used the movie reviews dataset, available in the nltk corpus. This dataset has actual review text annotated with their associated sentiments.   
  
To generate the testing data, we have used the SocioFi tool that is a third party application to extract actual Facebook comments in reaction to posts on the social media platform. This data is not labelled, and our model predicts the sentiment label based on the text in the comments.  
  <br/><br/>
**Tools Used**  
  
In this project, we will be using the TextBlob library which is one of  most efficient Natural Language Processing libraries in python.   
  
TextBlob: TextBlob is a Python (2 and 3) library for processing textual data. It  divides the preprocessing involved with sentiment analysis into common natural language processing (NLP) tasks such as part-of-speech tagging, noun phrase extraction, sentiment analysis, classification, translation, and more.    
  
To implement our project, we will be using the Jupyter Notebook.  
  
  
<br/><br/>
**Implementation**  
  
i)	To generate the corpus of negative and abusive phrases or words and factual negative 
phrases, we will use import and use the Selenium driver. The driver will scrape the web, and create a corpus of these phrases and words, that we will use as the abusive word corpus.  
  
ii)	From the TextBlob library, we import the nltk corpus. It includes the movie reviews 
dataset with labelled reactions that we will use as our training set.   
  
iii)	Next, we create a Naïve Bayes classifier, that trains on the review text available in 
the movie reviews, using the abusive word corpus, which generates a polarity and subjectivity score, for each of these texts, and a final label as abusive, negative, factual negative, neutral, positive etc. is predicted. Based on the actual label and the predicted label, the model learns.  
  
iv)	Similarly, we create a Support Vector Machines classifier, that trains on the same 
movie reviews dataset using the cyber bullying corpus.  
  
v)	For generating the testing data, we will use Socialfy that is a third party application to scrape Facebook and retrieve comments on posts. We will extract all the comments and reactions from Facebook along with the user id that are posted.  
  
vi)	The models are independently tested on these extracted Facebook comments. The 
models check the sentiment and subjectivity of each and every comment and set certain parameters according to the user beyond which negative sentiment should not be tolerated. 
  
vii)	For the comments which are predicted negative by the system, w the abusive words 
in that comment are found and mapped to the abusive word corpus.  
  
viii)	These comments are then classified into labels such as abusive, negative, factual negative, neutral and positive based on the models’ predictions, after they generate the polarity and subjectivity (fact-based) scores for each of these comments.  
  
ix)	After doing the above process we store the user ids and map it with the reaction user ids. If any user has posted any abusive stuff on the post but the reaction posted seems to be positive then it will not be booked under cyber bullying because it may have some sarcastic comment according to the admin of that post.   
  
x)	Finally we plot a bar graph for the percentage of comments in each category 
predicted by both the models separately. 

</BR> Licensed under [MIT License](LICENSE)
