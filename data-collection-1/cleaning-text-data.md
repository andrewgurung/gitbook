# Cleaning Text Data

### Step 0. Download data <a id="Step-1.-Sneak-peek-into-the-data"></a>

Note: In this tutorial, we will be using Kafka's "The Metamorphosis" where tells the story of salesman Gregor Samsa who wakes one morning to find himself inexplicably transformed into a huge insect.

Link: [http://www.gutenberg.org/cache/epub/5200/pg5200.txt](http://www.gutenberg.org/cache/epub/5200/pg5200.txt)

Open the file and delete the header and footer information and save the file as "metamorphosis\_clean.txt"

### Step 1. Sneak peek into the data <a id="Step-1.-Sneak-peek-into-the-data"></a>

* See structure, paragraph and punctuation of the data
* Determine how much of this data is useful for us
* Know your objective. For instance, if we are trying to develop a Kafka language model, we may want to keep the punctuation, quotes and cases

### Step 2. White space/Punctuation/Normalize Case <a id="Step-2.-Whitespace/Punctuation/Normalize-Case"></a>

### &lt; Manual cleaning &gt; <a id="&lt;-Manual-cleaning-&gt;"></a>

#### 2.1 Load data <a id="2.1-Load-data"></a>

```python
# 1. Load data
filename = 'metamorphosis_clean.txt'
file = open(filename, 'rt')
text = file.read()
file.close()
```

#### 2.2 Tokenization

Tokenization: Split paragraph -&gt; sentences -&gt; words. Commonly split by white spaces

* Split by white space
* Split by white space and remove punctuation

#### 2.2.a Split by white space <a id="2.2.a-Split-by-whitespace"></a>

Warning: We may end up with punctuation included. Eg: 'room,'

```python
# 2. Tokenization
# 2.2.a. split by whitespace
words = text.split()
print(words[:100])
```

#### Output: <a id="2.2.b-Split-by-whitespace-and-remove-punctuation"></a>

```text
'One', 'morning,', 'when', 'Gregor', 'Samsa', 'woke', 'from', 'troubled', 'dreams,', 'he', 'found', 'himself', 'transformed', 'in', 'his', 'bed', 'into', 'a', 'horrible', 'vermin.', 'He', 'lay', 'on', 'his', 'armour-like', 'back,', 'and', 'if', 'he', 'lifted', 'his', 'head', 'a', 'little', 'he', 'could', 'see', 'his', 'brown', 'belly,', 'slightly', 'domed', 'and', 'divided', 'by', 'arches', 'into', 'stiff', 'sections.', 'The', 'bedding', 'was', 'hardly', 'able', 'to', 'cover', 'it', 'and', 'seemed', 'ready', 'to', 'slide', 'off', 'any', 'moment.', 'His', 'many', 'legs,', 'pitifully', 'thin', 'compared', 'with', 'the', 'size', 'of', 'the', 'rest', 'of', 'him,', 'waved', 'about', 'helplessly', 'as', 'he', 'looked.', '"What\'s', 'happened', 'to', 'me?"', 'he', 'thought.', 'It', "wasn't", 'a', 'dream.', 'His', 'room,', 'a', 'proper', 'human'
```

#### 2.2.b Split by white space and remove punctuation <a id="2.2.b-Split-by-whitespace-and-remove-punctuation"></a>

* Create a mapping table
* Apply mapping table over a list to translate/strip punctuation

```python
# 2. Tokenization
# 2.2.b Split by whitespace and remove punctuation
Create a mapping table split by whitespace and remove punctuation
import string
words = text.split()

# list the characters in the punctuation constant
print(string.punctuation)

# create a mapping table
# where the 3rd parameter: list of characters to be removed
mappingTable = str.maketrans('', '', string.punctuation)

# apply mapping to remove punctuation
stripped = [w.translate(mappingTable) for w in words]
print(stripped[:100])
```

#### Output: <a id="2.3-Capitalization"></a>

```bash
!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~
['One', 'morning', 'when', 'Gregor', 'Samsa', 'woke', 'from', 'troubled', 'dreams', 'he', 'found', 'himself', 'transformed', 'in', 'his', 'bed', 'into', 'a', 'horrible', 'vermin', 'He', 'lay', 'on', 'his', 'armourlike', 'back', 'and', 'if', 'he', 'lifted', 'his', 'head', 'a', 'little', 'he', 'could', 'see', 'his', 'brown', 'belly', 'slightly', 'domed', 'and', 'divided', 'by', 'arches', 'into', 'stiff', 'sections', 'The', 'bedding', 'was', 'hardly', 'able', 'to', 'cover', 'it', 'and', 'seemed', 'ready', 'to', 'slide', 'off', 'any', 'moment', 'His', 'many', 'legs', 'pitifully', 'thin', 'compared', 'with', 'the', 'size', 'of', 'the', 'rest', 'of', 'him', 'waved', 'about', 'helplessly', 'as', 'he', 'looked', 'Whats', 'happened', 'to', 'me', 'he', 'thought', 'It', 'wasnt', 'a', 'dream', 'His', 'room', 'a', 'proper', 'human']
```

#### 2.3 Capitalization <a id="2.3-Capitalization"></a>

* Use .lower\(\) method to reduce every word to lowercase
* Warning: 'US' and 'us' may differ in meaning

```text
# 2.3 Capitalization
lowerWords = [w.lower() for w in stripped]
print(lowerWords[:100])
```

**Output:**

```text
['one', 'morning', 'when', 'gregor', 'samsa', 'woke', 'from', 'troubled', 'dreams', 'he', 'found', 'himself', 'transformed', 'in', 'his', 'bed', 'into', 'a', 'horrible', 'vermin', 'he', 'lay', 'on', 'his', 'armourlike', 'back', 'and', 'if', 'he', 'lifted', 'his', 'head', 'a', 'little', 'he', 'could', 'see', 'his', 'brown', 'belly', 'slightly', 'domed', 'and', 'divided', 'by', 'arches', 'into', 'stiff', 'sections', 'the', 'bedding', 'was', 'hardly', 'able', 'to', 'cover', 'it', 'and', 'seemed', 'ready', 'to', 'slide', 'off', 'any', 'moment', 'his', 'many', 'legs', 'pitifully', 'thin', 'compared', 'with', 'the', 'size', 'of', 'the', 'rest', 'of', 'him', 'waved', 'about', 'helplessly', 'as', 'he', 'looked', 'whats', 'happened', 'to', 'me', 'he', 'thought', 'it', 'wasnt', 'a', 'dream', 'his', 'room', 'a', 'proper', 'human']
```

### &lt; Using Natural Language Toolkit, or NLTK &gt; <a id="&lt;-Using-Natural-Language-Toolkit,-or-NLTK-&gt;"></a>

#### 2.1 Install NLTK <a id="2.1-Install-NLTK"></a>

* Install NLTK library
  * URL: [http://www.nltk.org/install.html](http://www.nltk.org/install.html)
* Download NLTK data\(toy grammar, trained models, etc\) ~3.25GB
  * URL: [http://www.nltk.org/data.html](http://www.nltk.org/data.html)

#### 2.2 Tokenization <a id="2.2-Tokenization"></a>

* Split by word: word\_tokenize\(text\)
* split by sentence: sent\_tokenize\(text\)
* Filter out punctuation: isalpha\(\)

#### 2.2.a Split by word <a id="2.2.a-Split-by-word"></a>

```python
# 1. load data
filename = 'metamorphosis_clean.txt'
file = open(filename, 'rt')
text = file.read()
file.close()

# 2. Tokenization
# 2a. Split into words
from nltk.tokenize import word_tokenize
tokens = word_tokenize(text)
print(tokens[:100])
```

Output:

```text
['One', 'morning', ',', 'when', 'Gregor', 'Samsa', 'woke', 'from', 'troubled', 'dreams', ',', 'he', 'found', 'himself', 'transformed', 'in', 'his', 'bed', 'into', 'a', 'horrible', 'vermin', '.', 'He', 'lay', 'on', 'his', 'armour-like', 'back', ',', 'and', 'if', 'he', 'lifted', 'his', 'head', 'a', 'little', 'he', 'could', 'see', 'his', 'brown', 'belly', ',', 'slightly', 'domed', 'and', 'divided', 'by', 'arches', 'into', 'stiff', 'sections', '.', 'The', 'bedding', 'was', 'hardly', 'able', 'to', 'cover', 'it', 'and', 'seemed', 'ready', 'to', 'slide', 'off', 'any', 'moment', '.', 'His', 'many', 'legs', ',', 'pitifully', 'thin', 'compared', 'with', 'the', 'size', 'of', 'the', 'rest', 'of', 'him', ',', 'waved', 'about', 'helplessly', 'as', 'he', 'looked', '.', '``', 'What', "'s", 'happened', 'to']
```

#### 2.2.b Split by sentence <a id="2.2.b-Split-by-sentence"></a>

```python
# 2b. Split by sentences
from nltk.tokenize import sent_tokenize
sentences = sent_tokenize(text)
print(sentences[:10])
```

Output:

```
['One morning, when Gregor Samsa woke from troubled dreams, he found\nhimself transformed in his bed into a horrible vermin.', 'He lay on\nhis armour-like back, and if he lifted his head a little he could\nsee his brown belly, slightly domed and divided by arches into stiff\nsections.', 'The bedding was hardly able to cover it and seemed ready\nto slide off any moment.', 'His many legs, pitifully thin compared\nwith the size of the rest of him, waved about helplessly as he\nlooked.', '"What\'s happened to me?"', 'he thought.', "It wasn't a dream.", 'His room,\na proper human room although a little too small, lay peacefully\nbetween its four familiar walls.', 'A collection of textile samples\nlay spread out on the table - Samsa was a travelling salesman - and\nabove it there hung a picture that he had recently cut out of an\nillustrated magazine and housed in a nice, gilded frame.', 'It showed\na lady fitted out with a fur hat and fur boa who sat upright,\nraising a heavy fur muff that covered the whole of her lower arm\ntowards the viewer.']
```

#### 2.2.c Filter out punctuation <a id="2.2.c-Filter-out-punctuation"></a>

```python
# 3. Filter out punctuation
tokens = word_tokenize(text)
# remove all tokens that are not alphabetic
words = [word for word in tokens if word.isalpha()]
print(words[:100])
```

```
['One', 'morning', 'when', 'Gregor', 'Samsa', 'woke', 'from', 'troubled', 'dreams', 'he', 'found', 'himself', 'transformed', 'in', 'his', 'bed', 'into', 'a', 'horrible', 'vermin', 'He', 'lay', 'on', 'his', 'back', 'and', 'if', 'he', 'lifted', 'his', 'head', 'a', 'little', 'he', 'could', 'see', 'his', 'brown', 'belly', 'slightly', 'domed', 'and', 'divided', 'by', 'arches', 'into', 'stiff', 'sections', 'The', 'bedding', 'was', 'hardly', 'able', 'to', 'cover', 'it', 'and', 'seemed', 'ready', 'to', 'slide', 'off', 'any', 'moment', 'His', 'many', 'legs', 'pitifully', 'thin', 'compared', 'with', 'the', 'size', 'of', 'the', 'rest', 'of', 'him', 'waved', 'about', 'helplessly', 'as', 'he', 'looked', 'What', 'happened', 'to', 'me', 'he', 'thought', 'It', 'was', 'a', 'dream', 'His', 'room', 'a', 'proper', 'human', 'room']
```

### Step 3. Stopwords + Stemming <a id="Step-3.-Stopwords-+-Stemming"></a>

#### 3.1 Stopwords <a id="3.1-Stopwords"></a>

Output:

Output:

Stopwords: Words with little value that are removed during NLP. Eg: the, and, me, myselfIn \[54\]:

```text
# 1. Import stopwords from NLTK library
from nltk.corpus import stopwords
print(stopwords.words('english'))
```

Output:

```text
['i', 'me', 'my', 'myself', 'we', 'our', 'ours', 'ourselves', 'you', "you're", "you've", "you'll", "you'd", 'your', 'yours', 'yourself', 'yourselves', 'he', 'him', 'his', 'himself', 'she', "she's", 'her', 'hers', 'herself', 'it', "it's", 'its', 'itself', 'they', 'them', 'their', 'theirs', 'themselves', 'what', 'which', 'who', 'whom', 'this', 'that', "that'll", 'these', 'those', 'am', 'is', 'are', 'was', 'were', 'be', 'been', 'being', 'have', 'has', 'had', 'having', 'do', 'does', 'did', 'doing', 'a', 'an', 'the', 'and', 'but', 'if', 'or', 'because', 'as', 'until', 'while', 'of', 'at', 'by', 'for', 'with', 'about', 'against', 'between', 'into', 'through', 'during', 'before', 'after', 'above', 'below', 'to', 'from', 'up', 'down', 'in', 'out', 'on', 'off', 'over', 'under', 'again', 'further', 'then', 'once', 'here', 'there', 'when', 'where', 'why', 'how', 'all', 'any', 'both', 'each', 'few', 'more', 'most', 'other', 'some', 'such', 'no', 'nor', 'not', 'only', 'own', 'same', 'so', 'than', 'too', 'very', 's', 't', 'can', 'will', 'just', 'don', "don't", 'should', "should've", 'now', 'd', 'll', 'm', 'o', 're', 've', 'y', 'ain', 'aren', "aren't", 'couldn', "couldn't", 'didn', "didn't", 'doesn', "doesn't", 'hadn', "hadn't", 'hasn', "hasn't", 'haven', "haven't", 'isn', "isn't", 'ma', 'mightn', "mightn't", 'mustn', "mustn't", 'needn', "needn't", 'shan', "shan't", 'shouldn', "shouldn't", 'wasn', "wasn't", 'weren', "weren't", 'won', "won't", 'wouldn', "wouldn't"]
```

```text
# 2. Tokenize words + remove punctuation
tokens = word_tokenize(text)
words = [word for word in tokens if word.isalpha()]

stop_words = set(stopwords.words('english'))
clean_words = [w for w in words if not w in stop_words]
print(clean_words[:100])
```

Output:

```text
['One', 'morning', 'Gregor', 'Samsa', 'woke', 'troubled', 'dreams', 'found', 'transformed', 'bed', 'horrible', 'vermin', 'He', 'lay', 'back', 'lifted', 'head', 'little', 'could', 'see', 'brown', 'belly', 'slightly', 'domed', 'divided', 'arches', 'stiff', 'sections', 'The', 'bedding', 'hardly', 'able', 'cover', 'seemed', 'ready', 'slide', 'moment', 'His', 'many', 'legs', 'pitifully', 'thin', 'compared', 'size', 'rest', 'waved', 'helplessly', 'looked', 'What', 'happened', 'thought', 'It', 'dream', 'His', 'room', 'proper', 'human', 'room', 'although', 'little', 'small', 'lay', 'peacefully', 'four', 'familiar', 'walls', 'A', 'collection', 'textile', 'samples', 'lay', 'spread', 'table', 'Samsa', 'travelling', 'salesman', 'hung', 'picture', 'recently', 'cut', 'illustrated', 'magazine', 'housed', 'nice', 'gilded', 'frame', 'It', 'showed', 'lady', 'fitted', 'fur', 'hat', 'fur', 'boa', 'sat', 'upright', 'raising', 'heavy', 'fur', 'muff']
```

#### 3.2 Stemming <a id="3.2-Stemming"></a>

Stemming reduces word to its root.

* leafs -&gt; leaf
* leaves -&gt; leav

```python
# 1. Import stemming model: Porter and Snowball
from nltk.stem.porter import PorterStemmer
porter = PorterStemmer()

# 2. Tokenize words + remove punctuation
tokens = word_tokenize(text)
words = [word for word in tokens if word.isalpha()]

# 3. Stemming of words
# Note: stemmed words are automatically in lowercase
stemmed = [porter.stem(word) for word in words]
print(stemmed[:100])
```

Output:

```text
['one', 'morn', 'when', 'gregor', 'samsa', 'woke', 'from', 'troubl', 'dream', 'he', 'found', 'himself', 'transform', 'in', 'hi', 'bed', 'into', 'a', 'horribl', 'vermin', 'He', 'lay', 'on', 'hi', 'back', 'and', 'if', 'he', 'lift', 'hi', 'head', 'a', 'littl', 'he', 'could', 'see', 'hi', 'brown', 'belli', 'slightli', 'dome', 'and', 'divid', 'by', 'arch', 'into', 'stiff', 'section', 'the', 'bed', 'wa', 'hardli', 'abl', 'to', 'cover', 'it', 'and', 'seem', 'readi', 'to', 'slide', 'off', 'ani', 'moment', 'hi', 'mani', 'leg', 'piti', 'thin', 'compar', 'with', 'the', 'size', 'of', 'the', 'rest', 'of', 'him', 'wave', 'about', 'helplessli', 'as', 'he', 'look', 'what', 'happen', 'to', 'me', 'he', 'thought', 'It', 'wa', 'a', 'dream', 'hi', 'room', 'a', 'proper', 'human', 'room']
```

### Step 4. Other tools <a id="Step-4.-Other-tools"></a>

* Lemmatization
  * Relates to stemming but more context aware
  * Accurate but slower. Useful for sentiment analysis
  * leafs -&gt; leaf
  * leaves -&gt; leaf
* Word embedding/Text vectors
  * Representing words as vectors
  * Words with similar context will be placed close in spatial position
  * Word2Vec: Most popular technique for lean word embedding.

