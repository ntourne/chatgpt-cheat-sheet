# ChatGPT Cheat Sheet
Most of the prompts listed below were obtained from the [ChatGPT Prompt Engineering for Developers](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) course from DeepLearning.AI and OpenAI.

Summarizing
-----------

Summarize text with a focus on specific topics.

**Text to summarize**

```
Got this panda plush toy for my daughter's birthday, 
who loves it and takes it everywhere. It's soft and super 
cute, and its face has a friendly look. It's a bit small 
for what I paid though. I think there might be other options 
that are bigger for the same price. It arrived a day 
earlier than expected, so I got to play with it myself b
efore I gave it to her.
```

**Summarize with a word/sentence/character limit**

```
Your task is to generate a short summary of a product 
review from an ecommerce site. 

Summarize the review below, delimited by triple 
backticks, in at most 30 words. 

Review: ```{content}```
```

**Summarize with a focus on shipping and delivery**

```
Your task is to generate a short summary of a 
product review from an ecommerce site to give 
feedback to the Shipping department. 

Summarize the review below, delimited by triple 
backticks, in at most 30 words, and focusing on any 
aspects that mention shipping and delivery of the product. 

Review: ```{content}```
```

**Summarize with a focus on price and value**

```
Your task is to generate a short summary of a 
product review from an ecommerce site to give 
feedback to the pricing department, responsible for 
determining the price of the product.  

Summarize the review below, delimited by triple 
backticks, in at most 30 words, and focusing on 
any aspects that are relevant to the price and 
perceived value. 

Review: ```{content}```
```

**Try "extract" instead of "summarize"**

```
Your task is to extract relevant information from 
a product review from an ecommerce site to give 
feedback to the Shipping department. 

From the review below, delimited by triple quotes 
extract the information relevant to shipping and 
delivery. Limit to 30 words. 

Review: ```{content}```
```


Inferring
---------

Infer sentiment and topics from product reviews and news articles.

**Product review text**

```
Needed a nice lamp for my bedroom, and this one had 
additional storage and not too high of a price point. 
Got it fast. The string to our lamp broke during the 
transit and the company happily sent over a new one.
Came within a few days as well. It was easy to put together. 
I had a missing part, so I contacted their support and 
they very quickly got me the missing piece! Lumina seems 
to me to be a great company that cares about their 
customers and products!!
```

**Sentiment (positive/negative)**

```
What is the sentiment of the following product review, which 
is delimited with triple backticks?

Review text: '''{content}''
```

```
What is the sentiment of the following product review, which 
is delimited with triple backticks?

Give your answer as a single word, either "positive" or "negative".

Review text: '''{content}'''
```

**Identify types of emotions**

```
Identify a list of emotions that the writer of the 
following review is expressing. Include no more than 
five items in the list. Format your answer as a list of 
lower-case words separated by commas.

Review text: '''{content}'''
```

**Identify anger**

```
Is the writer of the following review expressing anger?
The review is delimited with triple backticks. 
Give your answer as either yes or no.

Review text: '''{content}'''
```

**Extract product and company name from customer reviews**

```
Identify the following items from the review text: 
- Item purchased by reviewer
- Company that made the item

The review is delimited with triple backticks. 
Format your response as a JSON object with 
"Item" and "Brand" as the keys. 
If the information isn't present, use "unknown" 
as the value.
Make your response as short as possible.
  
Review text: '''{content}'''
```

**Doing multiple tasks at once**

```
Identify the following items from the review text: 
- Sentiment (positive or negative)
- Is the reviewer expressing anger? (true or false)
- Item purchased by reviewer
- Company that made the item

The review is delimited with triple backticks. 
Format your response as a JSON object with 
"Sentiment", "Anger", "Item" and "Brand" as the keys.
If the information isn't present, use "unknown" 
as the value.
Make your response as short as possible.
Format the Anger value as a boolean.

Review text: '''{content}'''
```

**Inferring topics**

Story:

```
In a recent survey conducted by the government, 
public sector employees were asked to rate their level 
of satisfaction with the department they work at. 
The results revealed that NASA was the most popular 
department with a satisfaction rating of 95%.

One NASA employee, John Smith, commented on the findings, 
stating, "I'm not surprised that NASA came out on top. 
It's a great place to work with amazing people and 
incredible opportunities. I'm proud to be a part of 
such an innovative organization."

The results were also welcomed by NASA's management team, 
with Director Tom Johnson stating, "We are thrilled to 
hear that our employees are satisfied with their work at NASA. 
We have a talented and dedicated team who work tirelessly 
to achieve our goals, and it's fantastic to see that their 
hard work is paying off."

The survey also revealed that the 
Social Security Administration had the lowest satisfaction 
rating, with only 45% of employees indicating they were 
satisfied with their job. The government has pledged to 
address the concerns raised by employees in the survey and 
work towards improving job satisfaction across all departments.
```

**Infer 5 topics**

```
Determine five topics that are being discussed in the 
following text, which is delimited by triple backticks.

Make each item one or two words long. 

Format your response as a list of items separated by commas.

Text sample: '''{content}'''
```

**Make a news alert for certain topics**

```
Determine whether each item in the following list of \
topics is a topic in the text below, which
is delimited with triple backticks.

Give your answer as list with 0 or 1 for each topic.\

List of topics: nasa, local government, engineering, 
employee satisfaction, federal government

Text sample: '''{story}'''
```
