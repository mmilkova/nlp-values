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
<li>Training SVM, LogitBoost, and LogisticRegression models based on embeddings from rubert-tiny2 for binary classification (spam|not spam) - <i>classification_to_filter_spam.ipynb</i></li></ul>
<br>
<li>Data annotation</li>
<br>
We use trial dataset (804 posts) and annotate it by experts, crowd-workers, and ChatGPT. Train dataset (5035 posts) is annotated by crowd-workers and ChatGPT.
Crowd-workers annotation is carrying out through Yandex.Toloka, and gpt-3.5-turbo model is used for ChatGPT annotation. The combination of crowd and ChatGPT is supposed to result in better accuracy.

<br>Folder <i>notebooks_annotation</i> contains scipts for:

<ul>
  <li>Using ChatGPT API to annotate text posts - <i>annotation_chatGPT.ipynb</i></li>
<li>Measuring reliability, accuracy and bias of annotation, along with the rules for combining of crowd and ChatGPT annotations – <i>annotation_analysis&combining.ipynb</i></li></ul>
<br>
<li>Building a classification to identify value-expressive posts</li>
<br>Folder <i>notebooks_values_binary_classification</i> contains scripts for binary classification of posts (value-expressive|value-inexpressive). SVM, LogitBoost, and LogitRegression models are used:

<ul>
<br>
<li>Script to fine-tune rubert-tiny2 (for 5 epochs) and use its 312-embedding, as well as use 768-embeddings from Conversational BERT – <i>rubert-tiny2_ConversationalRuBERT.ipynb</i></li>
<li>Script for using 1024-embeddings from SBERT – <i>SBERT.ipynb</i></li>
</ul>
</ol>
