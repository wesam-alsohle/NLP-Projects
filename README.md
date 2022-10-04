# Data Set:
books from Gutenberg where We read books and used a tokenizer from nltk library to divide the books Content into lines to use it in the trigram language model.

# Data preprocessing:
We creat some regular expressions Method to clean the data and then divided each sentence into words.

# build language model:
We build a trigram language model where the first thing we do padding the trigram sentences, then we create a dictionary and fill it with the probabilities of words coming after the previous two words so we can use it to choose the correct word later 𝑃(𝑤3|𝑤1,𝑤2).

After that We create some functions for correction matrix options, such as swapping letters, inserting letters for a word, deleting letters, and then creating methods to create three levels of word corrections.

# Correction Mechanism:
We take all the words without duplicates to create suggestions and then we take all the generated words after the previous two words of the trigram language model and then we pass by each suggestion:
if it exists in the generated words we take their probability to compare them with the rest of the suggestions to take the most likely suggestion and make it the correct output.
But if there are no words generated from the trigram language model, we take all the words without the repetitions and then calculate the number of repetitions of each word and the probability of its occurrence by:
dividing the number of word occurrences by the number of words in the data all to be used in a function to create suggestions and the probability of each suggestion.

After taking the suggestions and their probabilities, We choose the word that is more likely than the suggestions to be the correct word.
