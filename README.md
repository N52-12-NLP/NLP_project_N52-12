# NLP_project_N52-12

## Summarizator 3000X 

Program podsumowujący zawartość tekstową dokumentów za pomocą technologii przetwarzania języka naturalnego 

### Opis programu 
Program Summarizator 3000X działa w oparciu o przetwarzanie języka naturalnego. Jego celem jest tworzenie streszczeń dla wybranych dokumentów/tekstów, przy czym funkcja jest kompatybilna formatem '.pdf' i '.txt.' Dodatkową opcją jest wpisanie wartości tekstowej bezpośrednio w kodzie we wskazanym miejscu.  

Program umożliwia użytkownikowi wskazanie w jakim stopniu tekst ma być streszczony wyrażony w procentach (gdzie 100% to inicjalna objętość tekstowa) poprzez przeanalizowanie najczęściej powtarzających się wyrażeń i słów.  

Program został stworzony z myślą o streszczaniu artykułów naukowych. Z uwagi na to zaleca się, by teksty miały jednolitą tematykę w celu jak najlepszego działania algorytmów rozpoznających tekst.  

Program jest w stanie przetworzyć dokumenty zarówno w języku angielskim, jak i polskim. 

### Autorzy: 

Dawid Wróblewski 

Dawid Świercz 

Mariusz Lango 
 
### Licencje: 

MIT License 

  

Copyright (C) 2016-2022 ExplosionAI GmbH, 2016 spaCy GmbH, 2015 Matthew Honnibal 

Copyright (c) 2023 N52-12-NLP 

  

Permission is hereby granted, free of charge, to any person obtaining a copy 

of this software and associated documentation files (the "Software"), to deal 

in the Software without restriction, including without limitation the rights 

to use, copy, modify, merge, publish, distribute, sublicense, and/or sell 

copies of the Software, and to permit persons to whom the Software is 

furnished to do so, subject to the following conditions: 

 

The above copyright notice and this permission notice shall be included in all 

copies or substantial portions of the Software. 

  

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR 

IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, 

FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE 

AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER 

LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, 

OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE 

SOFTWARE. 

### Specyfikacja wymagań 

| ID  | Nazwa  | Opis  | Priorytet| Kategoria |
| ------------- | ------------- | --------- | ------------- | ------------- |
| 1 | Streszczanie tekstu   | Program ma przygotowywać streszczenia tekstów bazując na rankingu sentencji i słów kluczowych  | 1  | Funkcjonalne  |
| 2  | Streszaczanie do danego %   | Użytkownik będzie miał możliwość określania do jakiego stopnia (w %) teksty będą streszczane  | 2   | Funkcjonalne  |
| 3 | Analiza składowych   | Analizowane teksty rozkładane będą na poszczególne części mowy (wraz z ich odpowiednią kategoryzacją). Widoczna będzie również ilość wystąpień danej części mowy w tekście. Wynik powinien być pogrupowany malejąco według części mowy, a następnie posortowany według ilości wystąpień.  | 1  | Funkcjonalne |
| 4  | Analiza rzeczowników   | Program ma fitrować części mowy oraz prezentować najczęściej występujące rzeczowników w kolejności malejącej. Maksymalna liczba wyrażeń w wynikach będzie możliwa do określenia.  | 2  | Funkcjonalne |
| 5 | Analiza wyrażeń  | Program ma fitrować części mowy oraz prezentować najczęściej występujące rzeczowników w kolejności malejącej. Maksymalna liczba wyrażeń w wynikach będzie możliwa do określenia.  | 2   | Funkcjonalne  |
| 6  | Obsługa języka angielskiego   | Program obsługuję analizę tekstów w języku angielskim.  | 1  | Funkcjonalne  |
| 7 | Obsługa języka polskiego   | Program obsługuję analizę tekstów w języku polskim.  | 3   | Funkcjonalne  |
| 8  | Kategoryzacja tekstu  | Program, na podstawie analizy składowych tekstu, okrślać będzie kluczowe kategorie,  do których można przypisać główną tematykę analizowanego tekstu.  | 1 | Funkcjonalne  |
| 9 | Obsługa dokumentów pdf | Program ma tworzyć streszczenie dokumentów w formacie .PDF  | 1  | Funkcjonalne  |
| 10  | Obsługa dokumentów txt   | Program ma tworzyć streszczenie dokumentów w formacie .txt   | 2  | Funkcjonalne  |
| 11 | Obsługa tekstów skopiowanych  | Program ma tworzyć streszczenie dokumentów/treści wkljejonych ze schowka. | 2  | Funkcjonalne  |
| 12  | System Windows 64-bit   | Możliwośc obłsugi programu na Windows OS w wersji 64-bit  | 1  | Niefunkcjonalne  |

### Architektura rozwoju i uruchomienia 

Python version -- 3.9.7 

  

Projekt stworzony w środowisku Conda dla Windows 64-bit. Do instalacji pakietów wykorzystywane są zarówno metody pipeles jak i bezpośrednie adresy URL. 

Najnowsza wersja Pipeline dla Conda enviroment jest obowiązkowa! 

  

Niezbędne paczki: 

Spacy == 3.4.4 

spacy-legacy == 3.0.11 

spacy-loggers == 1.0.4 

### Testy programu 

| Lp. | Testowana funkcja          | Język     | system | plik / tekst wsadowy             | opis wyniku                                                                                                                                                                                                                                                                                                           |
|-----|----------------------------|-----------|--------|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1   | Import pliku PDF           | angielski | win64  | nlp.pdf                          | plik zaimportowany                                                                                                                                                                                                                                                                                                    |
| 2   | Streszaczanie do danego %  | angielski | win64  | nlp.pdf                          | tekst jest poprawnie skracany o wskazany %, wartość merytoryczna streszczenia nie była sprawdzana                                                                                                                                                                                                                     |
| 3   | Analiza składowych         | angielski | win64  | nlp.pdf                          | program błędnie interpretuje podwójny pusty znak (wynikający z wykresów, obrazów) jako rzeczownik, program interpretuje znak "-" jako przymiotnik, program rozróżnia wielkość liter- zliczył 2 wystapienia słowa chinese oraz 26 wystąpień słowa Chinese                                                              |
| 4   | Kategoryzacja tekstu       | angielski | win64  | nlp.pdf                          | program prawidłowo określa najczęściej występujące słowa oraz interpretuje jaka to częśc mowy natomiast nie potrafi otagować tekstu                                                                                                                                                                                   |
| 5   | analiza tekstu             | angielski | win64  | nlp.pdf                          | program osobno zlicza wyrazy w liczbnie pojedynczej oraz mnogiej- "word" 47 wystąpień, "words" 31 wystąpień,  program rozróżnia wielkość liter- zliczył 2 wystapienia słowa chinese (przymiotnik) oraz 26 wystąpień słowa Chinese (przymiotnik), program zinterpretował znak plusa oraz myślnika jako przymiotniki,   |
| 6   | Import pliku txt           | angielski | win64  | nlp.txt                          | plik zaimportowany                                                                                                                                                                                                                                                                                                    |
| 7   | Streszaczanie do danego %  | angielski | win64  | nlp.txt                          | tekst jest poprawnie skracany o wskazany %, wartość merytoryczna streszczenia nie była sprawdzana                                                                                                                                                                                                                     |
| 8   | Analiza składowych         | angielski | win64  | nlp.txt                          | program błędnie interpretuje podwójny pusty znak (wynikający z wykresów, obrazów) jako rzeczownik, program interpretuje znak "-" jako przymiotnik, program rozróżnia wielkość liter- zliczył 2 wystapienia słowa chinese oraz 26 wystąpień słowa Chinese                                                              |
| 9   | Kategoryzacja tekstu       | angielski | win64  | nlp.txt                          | program prawidłowo określa najczęściej występujące słowa oraz interpretuje jaka to częśc mowy natomiast nie potrafi otagować tekstu                                                                                                                                                                                   |
| 10  | analiza tekstu             | angielski | win64  | tekst skopiowany z pliku nlp.txt | program osobno zlicza wyrazy w liczbnie pojedynczej oraz mnogiej- "word" 47 wystąpień, "words" 31 wystąpień,  program rozróżnia wielkość liter- zliczył 2 wystapienia słowa chinese (przymiotnik) oraz 26 wystąpień słowa Chinese (przymiotnik), program zinterpretował znak plusa oraz myślnika jako przymiotniki,   |
| 11  | Analiza składowych         | angielski | win64  | tekst skopiowany z pliku nlp.txt | program błędnie interpretuje podwójny pusty znak (wynikający z wykresów, obrazów) jako rzeczownik, program interpretuje znak "-" jako przymiotnik, program rozróżnia wielkość liter- zliczył 2 wystapienia słowa chinese oraz 26 wystąpień słowa Chinese                                                              |
| 12  | Kategoryzacja tekstu       | angielski | win64  | tekst skopiowany z pliku nlp.txt | program prawidłowo określa najczęściej występujące słowa oraz interpretuje jaka to częśc mowy natomiast nie potrafi otagować tekstu                                                                                                                                                                                   |
| 13  | analiza tekstu             | angielski | win64  | tekst skopiowany z pliku nlp.txt | program osobno zlicza wyrazy w liczbnie pojedynczej oraz mnogiej- "word" 47 wystąpień, "words" 31 wystąpień,  program rozróżnia wielkość liter- zliczył 2 wystapienia słowa chinese (przymiotnik) oraz 26 wystąpień słowa Chinese (przymiotnik), program zinterpretował znak plusa oraz myślnika jako przymiotniki,   |
| 14  |                            | polski    |        |                                  | brak biblioteki z językiem polskim                                                                                                                                                                                                                                                                                    |
| 15  | tokeny                     | angielski | win64  | nlp.pdf                          | program prawidłowo dzieli tekst na poszczególne elementy                                                                                                                                                                                                                                                              |
| 16  | tokeny sentencji           | angielski | win64  | nlp.pdf                          | program interpertuje punktator (z kropką)  jako osobe zdanie, program interpretuje kropkę w dacie jako koniec zdania                                                                                                                                                                                                  |
| 17  | wyszukiwanie nazw własnych | angielski | win64  | nlp.pdf                          | program multiplikuje nazwy własne, wyświetlił wartość "English, 'LANGUAGE', 389" 389 razy, w tekscie słowo Eanglish nie (zawsze) było używane w kontekście języka. NLP zostało uznane za organizację,                                                                                                                 |
| 18  | tokeny                     | angielski | win64  | nlp.txt                          | program prawidłowo dzieli tekst na poszczególne elementy                                                                                                                                                                                                                                                              |
| 19  | tokeny sentencji           | angielski | win64  | nlp.txt                          | program interpertuje punktator (z kropką)  jako osobe zdanie, program interpretuje kropkę w dacie jako koniec zdania                                                                                                                                                                                                  |
| 20  | wyszukiwanie nazw własnych                                                   | angielski | win64  | nlp.txt                          | program multiplikuje nazwy własne, wyświetlił wartość "English, 'LANGUAGE', 389" 389 razy, w tekscie słowo Eanglish nie (zawsze) było używane w kontekście języka. NLP zostało uznane za organizację,                                                                                                                 |
| 21  | tokeny                                                                       | angielski | win64  | tekst skopiowany z pliku nlp.txt | program prawidłowo dzieli tekst na poszczególne elementy                                                                                                                                                                                                                                                              |
| 22  | tokeny sentencji                                                             | angielski | win64  | tekst skopiowany z pliku nlp.txt | program interpertuje punktator (z kropką)  jako osobe zdanie, program interpretuje kropkę w dacie jako koniec zdania                                                                                                                                                                                                  |
| 23  | wyszukiwanie nazw własnych                                                   | angielski | win64  | tekst skopiowany z pliku nlp.txt | program multiplikuje nazwy własne, wyświetlił wartość "English, 'LANGUAGE', 389" 389 razy, w tekscie słowo Eanglish nie (zawsze) było używane w kontekście języka. NLP zostało uznane za organizację,                                                                                                                 |
| 24  | porówanie podobieństwa dwóch tekstów na podstawie analizy składników tekstów | angielski | win 64 | npl.pdf, nlp2.pdf                | program wskazał wynik                                                                                                                                                                                                                                                                                                 |
| 25  | porówanie podobieństwa dwóch tekstów na podstawie analizy składników tekstów | angielski | win 64 | npl.txt, nlp2.txt                | program wskazał wynik                                                                                                                                                                                                                                                                                                 |
### Kod

```
# Import of all libraries

import spacy
from spacy.lang.en.stop_words import STOP_WORDS
from string import punctuation
from collections import Counter
from heapq import nlargest
from spacypdfreader import pdf_reader
import glob
from __future__ import print_function, unicode_literals
from collections import defaultdict
import re
from PyPDF2 import PdfReader
from spacy import displacy

# Trained language package (https://spacy.io/models/en)
nlp = spacy.load("en_core_web_sm")

# Loading text/file to analyze
      # IMPORTANT
      # Currently only 3 types of documents can be analyzed:
        # - .pdf (use solution 1)
        # - .txt (use solution 2)
        # - pasting data from clipboard (solution 3)


      # SOLUTION 1
        reader = PdfReader("C:/Your_path/Your_document.pdf") #Change path!
        text = ""
        for page in reader.pages:
            text += page.extract_text() + "\n"
        text = re.sub('\n', '', text)    

      # SOLUTION 2
      # Set path to your document
      path='C:/Your_path/Your_document.txt'
      for file in glob.glob(path):
          with open(file, encoding='utf-8', errors='ignore') as file_in:
              text = file_in.read()

      # SOLUTION 3
      # Paste your clipboard between ''
      text = ''


# Text Tokenization
doc=nlp(text)
tokens = [token.text for token in doc]
print(tokens)
punctuation = punctuation + '\n'

# Sentence print(tokens)
punctuation = punctuation + '\n'
doc = nlp(text)
sents_list = []
for sent in doc.sents:
    sents_list.append(sent.text)
print(sents_list)
punctuation = punctuation + '\n'

# Entity analysis
doc=nlp(text)
entities=[(i, i.label_, i.label) for i in doc.ents]
print(entities)

# Analysis of text composition      
def text_analyze(text): 
    doc=nlp(text)
    pos_counts = defaultdict(Counter)

    for token in doc:
        pos_counts[token.pos][token.orth] += 1

    for pos_id, counts in sorted(pos_counts.items()):
        pos = doc.vocab.strings[pos_id]
        for orth_id, count in counts.most_common():
            print(pos, count, doc.vocab.strings[orth_id])     
            
# Analysis of top used words and nouns  (second parameter describes how many records should be returned
def words_nouns(text,limit):
    doc=nlp(text)
    words = [token.text
             for token in doc
             if not token.is_stop and not token.is_punct]
    word_freq = Counter(words)
    common_words = word_freq.most_common(limit)
    # noun tokens that arent stop words or punctuations
    nouns = [token.text
             for token in doc
             if (not token.is_stop and
                 not token.is_punct and
                 token.pos_ == "NOUN")]
    noun_freq = Counter(nouns)
    common_nouns = noun_freq.most_common(limit)
    print("Common Worlds: ", common_words)
    print("Common Nouns: ", common_nouns)
    
 # Text summarization (second parametr describes in % how much original text should be summarized)
 def top_sentence(text, limit):
    keyword = []
    pos_tag = ['PROPN', 'ADJ', 'NOUN', 'VERB']
    doc = nlp(text.lower())
    sentences=len(list(doc.sents))
    break_point=(limit*sentences)/100
    for token in doc:
        if(token.text in nlp.Defaults.stop_words or token.text in punctuation):
            continue
        if(token.pos_ in pos_tag):
            keyword.append(token.text)
    
    freq_word = Counter(keyword)
    max_freq = Counter(keyword).most_common(1)[0][1]
    for w in freq_word:
        freq_word[w] = (freq_word[w]/max_freq)
        
    sent_strength={}
    for sent in doc.sents:
        for word in sent:
            if word.text in freq_word.keys():
                if sent in sent_strength.keys():
                    sent_strength[sent]+=freq_word[word.text]
                else:
                    sent_strength[sent]=freq_word[word.text]
    
    summary = []
    
    sorted_x = sorted(sent_strength.items(), key=lambda kv: kv[1], reverse=True)
    
    counter = 0
    for i in range(len(sorted_x)):
        summary.append(str(sorted_x[i][0]).capitalize())

        counter += 1
        #if(counter >= limit):
            #break
        if counter >= break_point:
            break
    return ' '.join(summary)
    
    
    
# Documents similarity
#Text 2
reader = PdfReader("""C:/Users\dawwr\Downloads\Brazil55-62.pdf""") #Change path!
text2 = ""
for page in reader.pages:
    text2 += page.extract_text() + "\n"
text2 = re.sub('\n', '', text2)  
doc = nlp("text")
doc2 = nlp("text2")
doc.similarity(doc2)


print(tokens)
punctuation = punctuation + '\n'
print(sents_list
punctuation = punctuation + '\n
print(entities)
text_analyze(text)
words_nouns(text,7)
top_sentence(text,80)
```
