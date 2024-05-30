# Imagination Tool: Public repository
This repository provides public resources related to the Imagination Tool Software developed by Fam Studio and the Creative Computing Institute, as described in the following paper:

Meriç, Melis, Seamus White, Alba Suárez Zapico, Zelda Yanovich, Bethany Koby-Hirschmann, and Rebecca Fiebrink. 2024. "Imagination Tool: Accessible AI Image Generation Software to Support Child Ideation and Creative Expression." Proceedings of the International Conference on Computational Creativity (ICCC). 17-21 June 2024.

Specifically, this repository uses word lists used in the above project to filter image generation prompts to attempt to improve safety for child users. 

We began by using a publicly available list of over 1300 "offensive/profane" English words list from [https://www.cs.cmu.edu/∼biglou/resources/](https://www.cs.cmu.edu/∼biglou/resources/). However, this list contained words that are not necessarily harmful (e.g., "fairy"), as well as words that would be unethical to prohibit (e.g., "black" or "asian") where the intention is to improve the safety of AI image generation tools. Consequently, we developed our custom "bad words" list by removing terms that our team deemed non-harmful. We then augmented the list to include any words _containing_ words on the list (e.g., "murder" is on the list; we added "murders" and "murdered"). However, this proved too stringent, with many words like "glass", "burgundy," and "hello" being prohibited (due to containing "ass," "gun," and "hell"). We therefore created a "safe words" list through (1) enumerating each word in the [NLTK](https://www.nltk.org/) Python library’s English words dataset which included as a substring any word on the "bad words" list; (2) employing the [alt-profanity-check](https://pypi.org/project/alt-profanity-check/) library to check whether each enumerated word was harmful; and (3) saving non-harmful enumerated words to a "safe words" list. These lists appear here for others to use and adapt.

(We do not claim that these resulting lists are perfect, nor appropriate for all users or use cases. We encourage others to adapt them as needed.)


