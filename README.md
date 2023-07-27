<h1>Detecting value-expressive text posts in Russian social media</h1>

This is the repository of the project.

<h2>Three steps of research</h2>
<ol>
<li>Data retrieving, preprocessing and filtering</li>

<br>Folder <i>notebooks_data_retrieving_filtering</i> contains scripts for:

  <ul>
<li>Using the VK API to retrieve posts from the walls of random users from the Russian social network VKontakte - <i>VKAPI_data_retrieving.ipynb</i></li>
<li>Preprocessing retrieved text data – <i>Preprocessing.ipynb</i></li>
<li>Using topic modeling (<a href=#artm>ARTM</a>) to extract bigrams that characterized spam posts - <i>TopicModeling.ipynb</i>. Folder <i>dictionaries&instructions</i> contains files (filter-words.txt, filter-words_if_linked.txt) with the most common bigrams to identify spam posts </li>
<li>Using simple rules for baseline classification to filter spam -  <i>Spam_filtering.ipynb</i></li>
<li>Training SVM, LogitBoost, and LogisticRegression models based on embeddings from <a href=#rubert-tiny2>rubert-tiny2</a> for binary classification (spam|not spam) - <i>classification_to_filter_spam.ipynb</i></li></ul>
<br>
<li>Data annotation</li>
<br>
We use trial dataset (804 posts) and annotate it by experts, crowd-workers, and ChatGPT. Train dataset (5035 posts) is annotated by crowd-workers and ChatGPT.
Crowd-workers annotation is carrying out through Yandex.Toloka, and gpt-3.5-turbo model is used for ChatGPT annotation. The combination of crowd and ChatGPT is supposed to result in better accuracy. The annotation guidline can be found in Instruction_for_ChatGPT.txt in <i>dictionaries&instructions</i> folder.

<br>Folder <i>notebooks_annotation</i> contains scipts for:

<ul>
  <li>Using ChatGPT API to annotate text posts - <i>annotation_chatGPT.ipynb</i></li>
<li>Measuring reliability, accuracy and bias of annotation, along with the rules for combining of crowd and ChatGPT annotations – <i>annotation_analysis&combining.ipynb</i></li></ul>
<br>
<li>Building a classification to identify value-expressive posts</li>
<br>Folder <i>notebooks_values_binary_classification</i> contains scripts for binary classification of posts (value-expressive|value-inexpressive). SVM, LogitBoost, and LogitRegression models are used:

<ul>
<br>

<li>Script to fine-tune rubert-tiny2 (for 5 epochs) and use its 312-embedding, as well as use 768-embeddings from <a href=#conversationalbert>Conversational RuBERT</a> – <i>rubert-tiny2_ConversationalRuBERT.ipynb</i></li>
<li>Script for using 1024-embeddings from <a href=#sbert>SBERT</a> – <i>SBERT.ipynb</i></li>
</ul>
</ol>
<h2>Data</h2>
According to ...
<h2>Citation</h2>
...
<h2>References</h2>
<a name="artm"></a> <a href='https://github.com/bigartm/bigartm' target='blank'>https://github.com/bigartm/bigartm</a> <br>
<a name="rubert-tiny2"></a>https://huggingface.co/cointegrated/rubert-tiny2 <br>
<a name="conversationalbert"></a>https://huggingface.co/DeepPavlov/rubert-base-cased-conversational  <br>
<a name="sbert"></a>https://huggingface.co/ai-forever/sbert_large_mt_nlu_ru  <br>
<h2>License</h2>
This project is licensed under the ... License
