The key words:

**1. Bag of Words (BoW)**: Counts how many time each word appears in a document.
**Ex**:
- `"free free money now"`
- Vocabulary=["free","money","now"]
- BoW Vector =[2,1,1]

**For Mathematical formula**

- If $w_i$= word in vocabulary and $d$=document, then 
$$BoW_i(d)=count \quad of \quad w_i \quad in \quad d$$


**2. Count Vectorizer**: Is the actual tool that applies **Bag of Words**in python. It does:

- Tokenization
- Lowercase
- Remove punctuation
- BoW counting
- Build vocabulary

**Mathematical idea**
CountVectorizer=BoW
$$Count_{ij}=TF(w_i,d_j)$$
It's raw word frequency.


**3. TF-IDF Vectorizer**: gives importance to rare words and reduces the weight of common words.

- Good words for spam detection:"free","prize","win","urgent","credit","loan"

- Bad or common words: "you","the","now","is"

TF-IDF Helps the model focus on meaningful words.

**Mathematical formula**

**1.Term Frequency(TF)**
$$TF(w,d)=\frac{Count(w,d)}{total\quad words \quad in\quad d}$$

**2. Document Frequency (df)**: Number of document containing word $w$.

**Inverse Document Frequency(IDF)**

$$IDF(w)=\log \frac{N}{df(w)}$$
where:
- $N$ = number of documents

- $df(w)$ = number of documents containing word w.

**Note that**: Rare words $\implies$ High IDF and Common words $\implies$ Low IDF

**3.TF-IDF Score**

$$TFIDF(w,d)=TF(w,d)\times IDF(w)$$

**Ex**:

``

D1: "free money now"

D2: "send money now"

``

Document frequency:

free $\rightarrow$ appears in 1 doc $\rightarrow$ high IDF

send $\rightarrow$ appears in 1 doc $\rightarrow$ high IDF

money $\rightarrow$ appears in 2 docs $\rightarrow$ low IDF

now $\rightarrow$ appears in 2 docs $\rightarrow$ low IDFs

Thus TF-IDF vectors emphasize:

free

send

More than:

money

now

**Main Differences between BoW,CountVectorizer and TF-IDF**
- BoW
Just a concept $\rightarrow$ word counts.

- CountVectorizer
Actual implementation of BoW.

- TF-IDF
 Improves BoW by giving more weight to rare, informative words.
 
