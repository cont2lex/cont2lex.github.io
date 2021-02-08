# Website for Cont2Lex

## 1. Intro

This website stores the essential resources for our AAAI-21 paper: 

Wenqiang Lei, Yisong Miao, Runpeng Xie, Bonnie Webber, Meichun Liu, Tat-Seng Chua and Nancy Chen (2021) **Have We Solved The Hard Problem? It’s Not Easy! Contextual Lexical Contrast as a Means to Probe Neural Coherence** (AAAI ‘21)

## 2. PDFs
- Paper for virtual presentation for AAAI in Feb 2021 (PDF) [Local Copy (PDF)](files/8523.LeiW.pdf)
- Slides (PDF) [To Come]()
- Poster (PDF) [Local Copy](files/WenqiangLei_NUS_Cont2Lex_Poster_v2.pdf) [BAAI AAAI-Beijing Meetup (PDF)](https://hub-cache.baai.ac.cn/hub-pdf/20201218/2/13-WenqiangLei_NUS_Cont2Lex_Poster.pdf) 



[Update on 8th Feb]: Yisong (the second author) has a substantial "one more thing" for this work, it may possibly lead to another paper. He will blog about it first in next few week. Stay tuned guys!



## 3. Cont2Lex Corpus
### 3.1 Quick Dive-In
Current version of the corpus is in `csv` format. Each line indicates one token of our corpus. Each token is constituted of w1, w2, context and a binary label indicating weather CLC holds. 

| w1      | w2     | context                                                      | label |
| ------- | ------ | ------------------------------------------------------------ | ----- |
| gold    | silver | December delivery **gold** fell $3.20 an ounce to $377.60.December **silver** declined 6.50 cents an ounce to $5.2180. | 0     |
| plant   | animal | One technique developed by some of these companies involves a chemical spray supposed to kill only a plant's pollen.But there have been problems with chemical sprays damaging **plants**' female reproductive organs and concern for the toxicity of such chemical sprays to humans, **animals** and beneficial insects. | 0     |
| kill    | save   | Some FAA officials note that few infants have been **killed** in plane crashes, raising the question of whether safety seats really are needed.A 1981 Harvard Medical School study that scrutinized accidents in the late 1970s concluded that perhaps three babies would have been **saved** in a five-year period if safety-seat use had been required. | 1     |
| current | old    | Under the agreement with the House and Senate leaders, the minimum wage would rise from the **current** $3.35 an hour to $4.25 an hour by April 1991.Employers could also pay a subminimum "training wage" for 90 days to new workers who are up to 19 years **old**, and then for another 90 days if the company institutes a specific training program for the newcomers. | 0     |
| quick   | slow   | Resistance to a national language comes primarily from members of the country's elite, who generally prefer English.But while better-off Filipinos are quick to cite the logic in using a language as widespread as English, they are often slow to reveal that they are prejudiced against Filipino, say advocates of the native language. "For the middle and upper-middle class {Filipino} is declasse," says Bien Lumbera, a Philippine-studies professor at Quezon City's University of the Philippines. | 1     |

Sample** to download: [Available here](files/cont2lex-samples.csv)

** We thank one anonymous reviewer's comment that we should indicate the offset of w1 and w2, so that we can avoid the duplication of w1 and w2 in one sentence. The full version will be made public when this issue is addressed. (very soon in Feb!)

Contact: Please contact Yisong with miaoyisong@gmail.com if you want a corpus leaving that issue unsolved. Thanks! 



### 3.2 Details

**Problem Definition**: Contextual Lexical Contrast (CLC): Two words are understood as contrast in order to understand the coherence of context. 

**Corpus Statistics:**

Cont2Lex Corpus contains 6,316 tokens, each of them is constituted of a context, two words showing up within them, and a well-annotated tag, indicating CLC is positive or not. 

**Source of Context**: The contexts are selected from widely used Wikipedia Corpus and Wall Street Journal Corpus, leaving an interface to connecting CLC with other NLP tasks.

**Source of Target Words**: The target words are carefully selected from ConceptNet's Antonym. We set a threshold of their contrasting degree at 0.25 in ConceptNet.

**Inter-Annotator Agreement (IAA)**: We calculate IAA using the consensus of our 5 annotators, reaching 75.3%.

**Positive Ratio (PR)**: Within all corpus, the Positive Ratio (ratio for positive CLC pairs) is 35.7%.

We also report the count and positive ratio w.r.t. different POS:

| POS   | #     | Positive Ratio |
| ----- | ----- | -------------- |
| Noun  | 2,413 | 33.2%          |
| Verb  | 1,568 | 27.9%          |
| Adj   | 2,081 | 43.7%          |
| Adv   | 254   | 40.9%          |
| Total | 6,316 | 35.7%          |

We can find that adj and adv have relatively higher PRs, this is in line with linguistic theory: the semantic dimensions of adj and adv are more focused. 



## 4. Code and Benchmarks

We provide the PyTorch implementation of our benchmark, including CLC benchmarks and out-of-context Lexical Contrast benchmarks. 

Coming soon.