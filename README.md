# PA-4-Spell-Correction

Programming Task

Your task is to create a program that

Takes an input w,
Determines whether or not there is a spelling error, and (spell detection)
Makes the best spelling suggestion (spell correction)
More specifically, you're to create your own error and language model using whatever data source you're able to find, but in case you'd like a little help in this area, please consider using the following:

For the error model: http://norvig.com/ngrams/count_1edit.txtLinks to an external site.
This file contains single-edit spelling correction edits and is based on Peter Norvig's collection of spelling mistakes. The data originates from Wikipedia. The actual words and their misspelling can be found at https://norvig.com/ngrams/spell-errors.txtLinks to an external site.
The file is structured in the following manner: w|c z ; where w is the wrong character, c is the correct, and z is the occurrence of the error
For example, in count_1edit.txt, there is 1 occurrence of B|M, where B was substituted M in the example My: By (here the correct word is My but it was misspelled as By).
You can normalize the counts based on your language model (i.e. count edit sequences in the corpus)
For the language model: NLTK's Gutenberg Corpus
Information: https://www.nltk.org/book/ch02.htmlLinks to an external site.
I also made a walk-through of using and collating all documents within the collection: Using_All_Project_Gutenberg_Documents_in_NLTK.ipynbDownload Using_All_Project_Gutenberg_Documents_in_NLTK.ipynb
The walk-through also gives you some brief statistics of the corpus
As previously mentioned, you can use your own data -- even the tweet data previously given -- but please make sure to cite your sources. This also extends to any code you might find online that could help. It is highly recommended, however, that you use the suggested resources above so that you don't waste time searching for data.

Here are some other assumptions to make:

You are expected to implement a model based on probabilities of spelling errors
Submissions that don't use error probabilities (i.e. generate all 1 edit words from the input word and then query the language model for the most probably word) will be accepted but will not merit full points
Limit your candidate words to an edit distance of 1 with respect to the input word w
Tip: When checking for alignment, break out of the edit distance computation if you find another error after the first error
Use cost of 1 per operation (Damerau-Levenshtein)
Limit your vocabulary to 1-grams
The task is centered on single-word inputs; therefore, you don't need to implement a 2-gram language model
ASSUME THAT ERROR CORRECTION WILL ONLY BE APPLIED IF AN ERROR IS DETECTED
E.g. If the was the input and it was found in your list of appropriately spelled words, then there your solution can assert that there's no error (see sample output)
I.e. No need to compute the probability of a non-error.
You are NOT allowed to use tools for the spell correction process itself
Please make sure you implement the models from scratch (i.e. extract the probabilities from some data source yourself, store them in some data structure, and query them accordingly) 
HOWEVER, you are free to use third-party libraries for tokenizing (e.g. NLTK) and extracting minimum edit distances (e.g. NLTK... diba? toolkit talaga 'tong NLTK na 'to).
You are also free to utilize any of your previous assessments, as well as any walk-throughs (e.g. language model), to help you in coming up with a solution for this assessment.
Please just make sure to note that all edit distance operations should have penalties equal 1
Sample Output
word
candidate
edit_type
edit
P(c)
P(w|c)
P(c) x P(w|c)
mohter
mother
tra
ht|th
0.000463
0.000094
4.337539e-08
mohter
morter
sub
h|r
0.000004
0.000012
5.010995e-11
Note that you are expected to provide all candidate words, their probabilities, and the values used to compute the probabilities. It would also help if your list was sorted -- showing the highest probability on top. Additionally, please note that the sample output may have different probability values than what you might have. You're free to test based on your own intuition.

Write Up Task
Like the previous assessments, there is a write-up component. As this is a group activity, please work together in coming up with your own write-up. You may either detail your thoughts independently from each other or integrate the ideas.

Use the following as a guide for coming up with your write-up:

Briefly describe the approach you took to implementing the spell correction assessment (both for detecting an error and correcting an error)
Did you make any modifications based from the method described in class?
What is an ideal corpus / edit distance matrix in relation to spell correction?
Do you think the corpus / edit distance matrix you used is good in relation to the task? Are there issues that you observed in using the data that might limit the performance of the model?
Are there ways we could modify the corpus / edit distance matrix to make the model more accommodating?
What can / can't your model do well? You may include examples.
Please note that you're not expected to create a perfect spell correction model, so there's no need to force the model to accommodate all known bugs of the model.
Do you think / can you imagine cases that the Noisy Channel cannot handle no matter what you do?
In general, use the write up as your chance to reflect on the topic and the exercise.

Submission Format
Just like with the previous assessments, there is no strict format to the assessment. If you need a template, consider working with the following file: PA4_Spell_Correction_template.ipynbDownload PA4_Spell_Correction_template.ipynb

If you use files that aren't automatically downloaded into the Python notebook, please include them in your submission.

Grade Breakdown
This assessment is worth 50 points -- 35 for the program correctness and 15 for the post-analysis. Rubrics for assessments are provided on the submission pages.

As this is considered group work, the grade assignment, by default, will be given equally. Please be considerate to your group mates and contribute as equally as possible. If you have issues with the contributions of group members, consider raising these issues with your instructor.
