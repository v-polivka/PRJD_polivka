# Načtení  knihoven
import pandas as pd
import matplotlib.pyplot as plt
from wordcloud import WordCloud
import nltk
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize
from textblob import TextBlob
import seaborn as sns

#nltk.download('punkt')
#nltk.download('stopwords')
#nltk.download('punkt_tab')

# Načtení datasetu
url = "https://raw.githubusercontent.com/Armita84/ChatGPT-Dataset-Reddit/refs/heads/main/chatgpt-reddit-comments.csv"
df = pd.read_csv(url)

# Prozkoumání datasetu
print(df.head())
print(df.info())
print(df.columns)

# Tokenizace a základní statistiky slov
all_text = " ".join(df['comment_body'].astype(str))  # 'comment_body' je sloupec s komentáři
tokens = word_tokenize(all_text.lower())
tokens = [word for word in tokens if word.isalpha() and word not in stopwords.words('english')]

print(f"Počet unikátních slov: {len(set(tokens))}")
print(f"Nejčastější slova: {pd.Series(tokens).value_counts().head(10)}")

# WordCloud
wordcloud = WordCloud(width=800, height=400, background_color='white').generate(" ".join(tokens))

plt.figure(figsize=(10, 5))
plt.imshow(wordcloud, interpolation="bilinear")
plt.axis('off')
plt.title('Nejčastější slova v komentářích')
plt.show()

# Sentiment analýza
def get_sentiment(text):
    blob = TextBlob(text)
    return blob.sentiment.polarity

df['sentiment'] = df['comment_body'].astype(str).apply(get_sentiment)

print(df[['comment_body', 'sentiment']].head())

# Vizualizace sentimentu
# Načtení  knihoven
import pandas as pd
import matplotlib.pyplot as plt
from wordcloud import WordCloud
import nltk
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize
from textblob import TextBlob
import seaborn as sns

nltk.download('punkt')
nltk.download('stopwords')
nltk.download('punkt_tab')

# Načtení datasetu
url = "https://raw.githubusercontent.com/Armita84/ChatGPT-Dataset-Reddit/refs/heads/main/chatgpt-reddit-comments.csv"
df = pd.read_csv(url)

# Prozkoumání datasetu
print(df.head())
print(df.info())
print(df.columns)

# Tokenizace a základní statistiky slov
all_text = " ".join(df['comment_body'].astype(str))  # 'comment_body' je sloupec s komentáři
tokens = word_tokenize(all_text.lower())
tokens = [word for word in tokens if word.isalpha() and word not in stopwords.words('english')]

print(f"Počet unikátních slov: {len(set(tokens))}")
print(f"Nejčastější slova: {pd.Series(tokens).value_counts().head(10)}")

# WordCloud
wordcloud = WordCloud(width=800, height=400, background_color='white').generate(" ".join(tokens))

plt.figure(figsize=(10, 5))
plt.imshow(wordcloud, interpolation="bilinear")
plt.axis('off')
plt.title('Nejčastější slova v komentářích')
plt.show()

# Sentiment analýza
def get_sentiment(text):
    blob = TextBlob(text)
    return blob.sentiment.polarity

df['sentiment'] = df['comment_body'].astype(str).apply(get_sentiment)

print(df[['comment_body', 'sentiment']].head())

# Výpočet základních statistik sentimentu
average_sentiment = df['sentiment'].mean()
median_sentiment = df['sentiment'].median()

print(f" Průměrný sentiment komentářů: {average_sentiment:.3f}")
print(f" Medián sentimentu komentářů: {median_sentiment:.3f}")

# Vizualizace sentimentu
plt.figure(figsize=(10, 5))
sns.histplot(df['sentiment'], bins=30, kde=True, color='purple')
plt.title('Rozdělení sentimentu komentářů')
plt.xlabel('Sentiment (Polarity)')
plt.ylabel('Počet komentářů')
plt.show()






