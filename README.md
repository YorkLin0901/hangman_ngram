# Hangman_solver
Candidate: Yukai Lin
Result: Achieved a 60.8% success rate, surpassing both the benchmark and the expected correct rate.

# Algorithm
As for a Hangman game, we need to guess all the letter within a word. According to Morphology, words in Standard English is constrcuted based on morpheme, the smallest unit of meaning. 
By learning morpheme construction rules, we can effectively approach solving Hangman games using n-gram methods.

1. N-gram

    For bigram, it is essential to identify the character most likely to follow a specific letter. Additionally, the probability of a character appearing immediately before the specific letter should also be considered. Therefore, our bigram set includes both the typical forward bigram and its reverse.

    For trigram, apart from considering the characters immediately before and after two consecutive letters, we should also seize the chance to predict a masked letter with 2 guessed letter on its two side. 

    This idea also works to ngram when $n > 3$. 

2. Word Boundary Information

    Certain letters are more likely to appear at the beginning or end of a word, e.g. "s". So if we add several * at the beginning and # at the end, We can learning the rule of letters being at the beginning and the end.

3. Strategy for Guessing the First Letter

    When attempting to guess the first letter, the optimal strategy is to choose the letter that appears with the highest frequency. This increases the likelihood of a correct guess. If the initial guess is incorrect, the strategy should be maintained until the first correct letter is identified.

    In this way, we mitigate the limitations of only having beginning and ending n-grams available when no letters have been correctly guessed. In such cases, guessing the most frequently occurring letter across all words is more advantageous than focusing on those that appear most often at the beginning or end of words.