# Text Suggestion System using Prefix Tree and N-Gram Model

This project implements a text suggestion system that uses a combination of a **Prefix Tree** (Trie) and an **N-Gram Language Model** to suggest the next words in a given text input. The system relies on a word frequency counter to provide accurate suggestions based on the context, considering both prefix-based word completions and context-based predictions using n-grams.

## Features

- **Word Completion**: Suggests the most probable word completions based on the prefix entered by the user.
- **Context-Aware Suggestions**: Uses an N-Gram model to suggest the next word based on the previous context (last N words).
- **Efficient Data Structures**: Utilizes a Prefix Tree for fast prefix-based word lookup and a defaultdict to store and query n-gram frequencies.
- **Probabilistic Approach**: Uses word frequencies and n-gram probabilities to generate word suggestions with higher likelihood.

## Project Structure

1. **PrefixTreeNode**: A node of the prefix tree containing children nodes and a flag to indicate whether it's the end of a word.
2. **PrefixTree**: A data structure (Trie) for efficiently storing words and searching for words starting with a given prefix.
3. **WordCompletor**: A class that uses the Prefix Tree and word frequencies to suggest completions for a given word prefix.
4. **NGramLanguageModel**: A language model based on n-grams that predicts the next word based on the previous N words.
5. **TextSuggestion**: A high-level class that integrates both word completion and n-gram models to generate the most relevant suggestions.

## How it Works

### 1. Word Completion using Prefix Tree
The **Prefix Tree** allows for efficient word completion based on a given prefix. By traversing the tree according to the input prefix, the system retrieves all possible words that start with the given prefix.

The **WordCompletor** class utilizes the Prefix Tree along with word frequency data to suggest word completions. It prioritizes more frequent words, improving the relevance of the suggestions.

### 2. N-Gram Model for Context-Aware Suggestions
The **N-Gram Language Model** is trained on a corpus of text and calculates the probability of a word following a given sequence of the last N words (in this case, trigrams).

The **TextSuggestion** class integrates this N-Gram model to provide word suggestions based on the context of the last few words typed, allowing for more intelligent and context-aware word predictions.

### 3. Combining Both Models
The system first suggests word completions using the **Prefix Tree** based on the given prefix.

Once the first word is completed, the **N-Gram model** is then used to predict subsequent words, providing context-aware suggestions for the rest of the input. This combination of prefix-based and context-based suggestions results in a more accurate and fluent text prediction system.


## Requirements

- **Python 3.x**
- **`numpy`**
- **`tqdm`**
- **`re`**

You can install the required dependencies using:

```bash
pip install numpy tqdm
 
