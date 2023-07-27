<b>Detecting value-expressive text posts in Russian social media</b>

This is the repository of the project.

Three steps of research:
<ol>
<li>Data retrieving, preprocessing and filtering</li>

<br>Folder <i>notebooks_data_retrieving_filtering</i> contains scripts for:

  <ul>
<li>Using the VK API to retrieve posts from the walls of random users from the Russian social network VKontakte - <i>VKAPI_data_retrieving.ipynb</i></li>
<li>Preprocessing retrieved text data – <i>Preprocessing.ipynb</i></li>
<li>Using topic modeling (ARTM) to extract bigrams that characterized spam posts - <i>TopicModeling.ipynb</i></li>
<li>Using simple rules for baseline classification to filter spam -  <i>Spam_filtering.ipynb</i></li>
<li>Training SVM, LogitBoost, and LogisticRegression models based on embeddings from rubert-tiny2 for binary classification (spam|not spam) - classification_to_filter_spam.ipynb</li></ul>
<li>Data annotation</li>
We use trial dataset (804 posts) and annotate it by experts, crowd-workers, and ChatGPT. Train dataset (5035 posts) is annotated by crowd-workers and ChatGPT.
Crowd-workers annotation is carrying out through Yandex.Toloka, and gpt-3.5-turbo model is used for ChatGPT annotation. 
The combination of crowd and ChatGPT is supposed to result in better accuracy.
Folder notebooks_annotation contains scipts for:
Using ChatGPT API to annotate text posts - annotation_chatGPT.ipynb
Measuring reliability, accuracy and bias of annotation, along with the rules for combining of crowd and ChatGPT annotations – annotation_analysis&combining.ipynb
3.	Building a classification to identify value-expressive posts
Folder notebooks_values_binary_classification contains scripts for binary classification of posts (value-expressive|value-inexpressive). SVM, LogitBoost, and LogitRegression models are used:
Script to fine-tune rubert-tiny2 (for 5 epochs) and use its 312-embedding, as well as use 768-embeddings from Conversational BERT – rubert-tiny2_ConversationalRuBERT.ipynb
Script for using 1024-embeddings from SBERT – SBERT.ipynb

