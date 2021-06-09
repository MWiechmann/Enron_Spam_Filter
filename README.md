# Building a Spam Filter with Naive Bayes
Here I build a simple (but effective) spam filter for E-Mails using a naive Bayes approach on the Enron Spam Dataset. So far I am just scanning the subject line of the email. This approach with no further fine-tuning detects 100% of the spam in the test dataset, and only classifies 4% of "ham" messages incorrectly.

Contents of this repo

File|Details
-|-
/data|data files see below for details
Building a Spam Filter with Naive Bayes.ipynb|Jupyter Notebook with the python code to build the Spam Filter
process_data.py|Python script to fetch data from repo and pre-process it (as seperate script so it can run in the background with low priorities if needed)

## Contents of /data
File|Content
-|-
enron_spam_data.zip | The raw Enron-Spam data set from my repo [here](https://github.com/MWiechmann/enron_spam_data). A zipped csv-file that contains the columns Subject (subject line), Message (email body), Spam/Ham (email category encoded "ham" or "spam") and Date (date of the email in the format YYYY-MM-DD)
train.zip | 80% of the original data set for training the model. The structure is similar to the the Enron-Spam data (above), but Subject and Message have been preprocessed: The string has been converted to lowercase, punctuation has been removed. Additionally, the string has been converted to a list with one value per word.
test.zip | 20% of the original data set for testing the model. No further preprocessing has been done on this data.
subject_voc.zip | Zipped csv-file that contains the word count of all unique words from the subject line (based on the training data). Each unique word is represented by a column and each subject line of the train is represented by a single line. So each line contains the word count per word for this subject line.
message_voc_zip | Zipped csv file with the vocabulary for the email text bodies. Structure is identical to subject_voc.zip (above) so each line contains the word count per word for a single email message body.
