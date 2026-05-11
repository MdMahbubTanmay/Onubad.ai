# Heres a Guideline how to contribute on Datasets
Since we are training NLLB - A standaredise format that we will follow is given below:
```jsonl
{"translation": {"en": "YOUR_ENGLISH_SENTENCE_GOES_HERE", "bn": "YOUR_BANGLA_TRANSLATION_GOES_HERE"}}
```

## Folder Structure:

```txt
data/
├── raw/                # Raw data (unprocessed)
├── processed/          # Clean and Validated data for training
```

## Rules to Collect Data:
- We are aiming to collect 20k pair of translation
- 70% of data are Sentence to Sentence and 30% of data are Paragraph by Paragraph (20 - 30 Words in a sentence)
- 80% of Data are Synthetic Data (with Human in Loop Validation) , 20% data are Real data
- We will use different models like (Gemini, Claude, GPT-4) to generate synthetic data and it must be validated with Human in Loop Validation
- Use multiple instances of same English Sentence with different Bangla Translations to increase the diversity of the dataset and avoid overfitting
- Avoid using very common sentences that are likely to be found in existing datasets to ensure the uniqueness of our dataset
- Use 50% of data are Back Translation eg. Bangla to English to Bangla . 
- For Validation keep 10% of data as validation 5-10% data set as Testing set and 80% of data as training set.

## Sources to Collect Data:
- We can scrape data from Bangla news websites, blogs, and social media platforms to collect real sentences and their translations.
- We can scrape data from Bangla PDF books, Novels, and other literature to collect real sentences and their translations.
- We can Use Idioms, Proverbs, and Common Phrases in Bangla to create unique sentence pairs.
- We can Use Generate Synthetic Data using different models like (Gemini, Claude, GPT-4) to create unique sentence pairs.

## Validation Process:
- Human will recheck the generated data and edit the translation make it very natural and fluent.


## Example of a Validated Data:
```jsonl
{"translation": {"en": "The cat is on the roof.", "bn": "বিড়ালটা ছাদের ওপর বসে আছে।"}}
{"translation": {"en": "She loves to read books.", "bn": "ও বই পড়তে খুব ভালোবাসে।"}}
{"translation": {"en": "The weather is nice today.", "bn": "আজকের আবহাওয়াটা বেশ দারুণ, তাই না?"}}
{"translation": {"en": "I am going to the market.", "bn": "আমি একটু বাজারে যাচ্ছি রে।"}}
{"translation": {"en": "He is a good friend.", "bn": "ও কিন্তু হেব্বি ভালো বন্ধু।"}}

// Add more variant one same datasets

// Variation 1

{"translation": {"en": "The cat is on the roof", "bn": "বেড়ালটা তো ছাদের ওপর রে!"}}
{"translation": {"en": "She loves to read books", "bn": "ও তো বই পড়তে খুব ভালোবাসে রে।"}}
{"translation": {"en": "The weather is nice today", "bn": "আজকের আবহাওয়াটা বেশ দারুণ, তাই না রে?"}}
{"translation": {"en": "I am going to the market", "bn": "আমি তো এখন বাজারে যাচ্ছি রে।"}}
{"translation": {"en": "He is a good friend", "bn": "ও কিন্তু খুব ভালো বন্ধু রে।"}}

// Variation 2

{"translation": {"en": "The cat is on the roof", "bn": "দেখুন, বিড়ালটি কিন্তু এখন ছাদের ওপরেই অবস্থান করছে।"}}
{"translation": {"en": "She loves to read books", "bn": "উনি তো আসলে বই পড়তে ভীষণ রকমের পছন্দ করেন।"}}
{"translation": {"en": "The weather is nice today", "bn": "আজকের আবহাওয়াটা সত্যি বলতে বেশ চমৎকার এবং মনোরম, তাই না?"}}
{"translation": {"en": "I am going to the market", "bn": "আমি আসলে এখন বাজারের দিকেই যাচ্ছি।"}}
{"translation": {"en": "He is a good friend", "bn": "উনি মানুষ হিসেবে অত্যন্ত অমায়িক এবং সত্যিই খুব ভালো একজন বন্ধু।"}}

// Variation 3

{"translation": {"en": "The cat is on the roof", "bn": "বিড়ালটা কিন্তু এখন ছাদের ওপর গিয়ে বসে আছে।"}}
{"translation": {"en": "She loves to read books", "bn": "ও তো আসলে বই পড়তে ভীষণ ভালোবাসে।"}}
{"translation": {"en": "The weather is nice today", "bn": "আজকের আবহাওয়াটা বেশ চমৎকার আর আরামদায়ক।"}}
{"translation": {"en": "I am going to the market", "bn": "আমি আসলে এখন দরকারি কিছু কেনাকাটা করার জন্য বাজারের দিকে যাচ্ছি।"}}
{"translation": {"en": "He is a good friend", "bn": "ও মানুষ হিসেবে সত্যিই খুব দারুণ।"}}

... and more
```

## Prompt Ideas to follow

#### Casual Vibe

```txt
Act as a native Bengali speaker in a very casual, intimate setting. Translate the following text into "Tui" (তুই) register. Use colloquial filler words like 'রে' (re), 'তো' (to), 'আরে' (arey), and 'বাপরে' (bapre) to make it sound natural. The tone should be friendly, informal, and relaxed. Avoid any formal words.
```

#### Semi-Formal/Friendly Vibe

```txt
Act as a native Bengali linguist specializing in modern "Cholitobhasha." Translate the text using the "Tumi" (তুমি) register. The translation should be warm and descriptive, adding extra contextual words to make the sentences feel complete and engaging rather than brief. Avoid literal translation; focus on how a person would naturally explain things to a friend.
```

#### Formal Vibe

```txt
Act as a professional Bengali translator. Translate the text into the "Apni" (আপনি) register. Use polite, sophisticated, and respectful vocabulary. The sentences should be detailed, well-structured, and slightly longer to reflect a formal and courteous manner. Ensure the tone is dignified and culturally appropriate for a formal conversation.
```

#### Expressive/Storytelling Vibe

```txt
Translate the following into Bengali with a deep emotional and expressive tone. Use descriptive adjectives and culturally resonant metaphors. The sentences should feel like part of a story or a heartfelt conversation. Ensure it captures the "soul" of the message rather than just the words.
```

#### Urban/Gen-Z

```txt
Act as a modern, urban Bengali speaker. Translate the text into a "Banglish" style, where technical or common English terms are transliterated into Bengali script (e.g., 'Internet' as ইন্টারনেট). The tone should be trendy and reflects how Gen-Z or young professionals in Dhaka/Kolkata talk today. Use the "Tumi" register.
```

---

<details>
<summary>Metadata (Click to expand)</summary>
- Author: Irshad Hossain <br>
- Last Updated: May 11, 2026 <br>
- Latest Contributor: Irshad Hossain <br>
</details>