# PRJD_polivka
Metody
NLTK - Natural Language Toolkit
NLTK je přední open source knihovna pro zpracování přirozeného jazyka v Pythonu. Nabízí jednoduché rozhraní k více než 50 jazykovým korpusům a zdrojům (např. WordNet) a obsahuje nástroje pro klasifikaci, tokenizaci, stemming, tagování, syntaktickou analýzu a sémantické zpracování textu. Je vhodná pro lingvisty, studenty, vývojáře i výzkumníky a funguje na Windows, Mac i Linuxu. Součástí je i kniha Natural Language Processing with Python, která prakticky seznamuje s programováním v oblasti jazykového zpracování. NLTK je ceněna jako výborný nástroj pro výuku i vývoj v oblasti výpočetní lingvistiky.
V kódu je NLTK použita na tokenizaci a filtrování běžných slov. 
word_tokenize(...) – rozdělí text na jednotlivá slova pomocí NLTK (přesněji punkt tokenizer).

stopwords.words('english') – poskytne seznam anglických stop slov, která jsou poté z textu odfiltrována.

Worldcloud
WordCloud je vizuální nástroj pro znázornění frekvence slov v textu. Čím častěji se dané slovo vyskytuje, tím větší a výraznější se v mraku zobrazí. Tento nástroj se často používá v analýze textu, protože umožňuje rychle a intuitivně zachytit hlavní témata nebo často zmiňované pojmy. 


V kódu pracuje tento nástroj s tokeny (jednotlivá slova získaná z předchozího kroku). Ty jsou následně zobrazeny v grafu, který zobrazuje nejčastější slova dle velikosti.

Analýza sentimentu

Knihovna TextBlob - je knihovna jazyka Python pro zpracování textových dat. Poskytuje jednoduché rozhraní API pro běžné úlohy zpracování přirozeného jazyka (NLP), jako je označování částí řeči, extrakce podstatných jmen, analýza sentimentu, klasifikace a další. TextBlob stojí na ramenou NLTK a pattern a spolupracuje dobře s oběma knihovnami.
Analýza sentimentu je technikou z oblasti strojového zpracování přirozeného jazyka (NLP). Jedná se o automatické rozpoznání postoje, názoru či emoce. Toto rozpoznávání je pak nejčastěji řezeno na spektru pozitivní-neutrální-negativní.
Modely založené na transformátorech, jako jsou BERT a LSTM, přinášejí pokročilé možnosti analýzy sentimentu. Tyto modely zachycují slovní vztahy a kontext, což je činí ideálními pro rozsáhlé úlohy s různými nuancemi. Vyžadují sice značný výpočetní výkon a rozsáhlé soubory dat, ale díky své přesnosti jsou nejlepší volbou pro aplikace, jako je analýza podrobné zpětné vazby nebo textů specifických pro danou oblast. 
TextBlob je snadno použitelná knihovna, ideální pro začátečníky nebo rychlé vyhodnocování sentimentu. Její metoda .sentiment poskytuje skóre polarity s minimálním nastavením. TextBlob je ideální pro menší projekty a přímočaré úlohy, kde je klíčová snadná implementace.
Modul textblob.sentiments obsahuje dvě implementace analýzy sentimentu: PatternAnalyzer (založený na knihovně vzorů) a NaiveBayesAnalyzer (klasifikátor NLTK vycvičený na korpusu filmových recenzí). Výchozí implementací je PatternAnalyzer, ale analyzátor můžete přepsat předáním jiné implementace do konstruktoru TextBlob. Například NaiveBayesAnalyzer vrací svůj výsledek jako pojmenovanou dvojici ve tvaru: Sentiment(classification, p_pos, p_neg).
Výhody: Vhodné pro začátečníky, snadná integrace, Nízké nároky na zdroje, lze spustit na základním hardwaru.
Nevýhody: nejsou optimalizovány pro emotikony, slang nebo psaní velkých písmen, Omezená škálovatelnost, nejvhodnější pro menší soubory dat.



Výsledky
Počet unikátních slov: 34403
Nejčastější slova:
ai         9787
chatgpt    9573
like       9524
would      7453
people     7209
use        5181
get        5048
think      4957
one        4668
even       4331


Analýza sentimentu
Na základě údajů z analýzy sentimentu můžeme pozorovat, že jsou komentáře na Redditu z daného datasetu převážně neutrální až pozitivní. Průměrný sentiment komentářů činí  0.095, což tedy ukazuje na mírnou pozitivity a medián sentimentu komentářů je 0.029.



