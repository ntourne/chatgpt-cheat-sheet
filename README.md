# ChatGPT Cheat Sheet
These prompts listed below were obtained from the [ChatGPT Prompt Engineering for Developers](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) course by DeepLearning.AI and OpenAI.

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

Review text: ```{content}```
```

```
What is the sentiment of the following product review, which 
is delimited with triple backticks?

Give your answer as a single word, either "positive" or "negative".

Review text: ```{content}```
```

**Identify types of emotions**

```
Identify a list of emotions that the writer of the 
following review is expressing. Include no more than 
five items in the list. Format your answer as a list of 
lower-case words separated by commas.

Review text: ```{content}```
```

**Identify anger**

```
Is the writer of the following review expressing anger?
The review is delimited with triple backticks. 
Give your answer as either yes or no.

Review text: ```{content}```
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
  
Review text: ```{content}```
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

Review text: ```{content}```
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

Text sample: ```{content}```
```

**Make a news alert for certain topics**

```
Determine whether each item in the following list of \
topics is a topic in the text below, which
is delimited with triple backticks.

Give your answer as list with 0 or 1 for each topic.\

List of topics: nasa, local government, engineering, 
employee satisfaction, federal government

Text sample: ```{content}```
```

Transforming
------------

How to use LLM for text transformation tasks such as language translation, spelling and grammar checking, tone adjustment, and format conversion.

**Translation**

ChatGPT is trained with sources in many languages. This gives the model the ability to do translation. Here are some examples of how to use this capability.

```
Translate the following English text to Spanish: 
```Hi, I would like to order a blender``
```

```
Tell me which language this is: 
```Combien coûte le lampadaire?```
```

```
Translate the following  text to French and Spanish
and English pirate: 
```I want to order a basketball```
```

```
Translate the following text to Spanish in both the 
formal and informal forms: 
'Would you like to order a pillow?'
```

**Tone Transformation**

Writing can vary based on the intended audience. ChatGPT can produce different tones.

```
Translate the following from slang to a business letter: 
'Dude, This is Joe, check out this spec on this standing lamp.
```

**Format Conversion**

ChatGPT can translate between formats. The prompt should describe the input and output formats.

```python
data_json = { "resturant employees" :[ 
    {"name":"Shyam", "email":"shyamjaiswal@gmail.com"},
    {"name":"Bob", "email":"bob32@gmail.com"},
    {"name":"Jai", "email":"jai87@gmail.com"}
]}
```

```
Translate the following python dictionary from JSON to an HTML 
table with column headers and title: {data_json}
```

**Spellcheck/Grammar check**

```
Its going to be a long day. Does the car need it’s oil changed
```

```
Proofread and correct the following text
and rewrite the corrected version. If you don't find and errors, just say "No errors found". Don't use any punctuation around the text:
```{content}```
```

```
Got this for my daughter for her birthday cuz she keeps taking 
mine from my room. Yes, adults also like pandas too. She takes 
it everywhere with her, and it's super soft and cute. One of the 
ears is a bit lower than the other, and I don't think that was 
designed to be asymmetrical. It's a bit small for what I paid for it 
though. I think there might be other options that are bigger for 
the same price. It arrived a day earlier than expected, so I got 
to play with it myself before I gave it to my daughter.
```

```
Proofread and correct this review:
```{content}```
```

```
Proofread and correct this review. Make it more compelling. 
Ensure it follows APA style guide and targets an advanced reader. 
Output in markdown format.
Text: ```{content}```
````

Expanding
---------

Generate customer service emails that are tailored to each customer's review.

**Customize the automated reply to a customer email**

```
So, they still had the 17 piece system on seasonal 
sale for around $49 in the month of November, about 
half off, but for some reason (call it price gouging) 
around the second week of December the prices all went 
up to about anywhere from between $70-$89 for the same 
system. And the 11 piece system went up around $10 or 
so in price also from the earlier sale price of $29. 
So it looks okay, but if you look at the base, the part 
where the blade locks into place doesn’t look as good 
as in previous editions from a few years ago, but I 
plan to be very gentle with it (example, I crush 
very hard items like beans, ice, rice, etc. in the 
blender first then pulverize them in the serving size 
I want in the blender then switch to the whipping 
blade for a finer flour, and use the cross cutting blade 
first when making smoothies, then use the flat blade 
if I need them finer/less pulpy). Special tip when making 
smoothies, finely cut and freeze the fruits and 
vegetables (if using spinach-lightly stew soften the 
spinach then freeze until ready for use-and if making 
sorbet, use a small to medium sized food processor) 
that you plan to use that way you can avoid adding so 
much ice if at all-when making your smoothie. 
After about a year, the motor was making a funny noise. 
I called customer service but the warranty expired 
already, so I had to buy another one. FYI: The overall 
quality has gone done in these types of products, so 
they are kind of counting on brand recognition and 
consumer loyalty to maintain sales. Got it in about 
two days.
```

```
You are a customer service AI assistant.
Your task is to send an email reply to a valued customer.
Given the customer email delimited by ```, 
Generate a reply to thank the customer for their review.
If the sentiment is positive or neutral, thank them for 
their review.
If the sentiment is negative, apologize and suggest that 
they can reach out to customer service. 
Make sure to use specific details from the review.
Write in a concise and professional tone.
Sign the email as `AI customer agent`.
Customer review: ```{content}```
Review sentiment: negative
```

**Remind the model to use details from the customer's email**

```
You are a customer service AI assistant.
Your task is to send an email reply to a valued customer.
Given the customer email delimited by ```, 
Generate a reply to thank the customer for their review.
If the sentiment is positive or neutral, thank them for 
their review.
If the sentiment is negative, apologize and suggest that 
they can reach out to customer service. 
Make sure to use specific details from the review.
Write in a concise and professional tone.
Sign the email as `AI customer agent`.
Customer review: ```{content}```
Review sentiment: negative
```

Chatbot
-------

How you can utilize the chat format to have extended conversations with chatbots personalized or specialized for specific tasks or behaviors.

**OrderBot**

We can automate the collection of user prompts and assistant responses to build a OrderBot. The OrderBot will take orders at a pizza restaurant.

```json
 {
   "role": "system",
   "content": "You are OrderBot, an automated service to collect orders 
      for a pizza restaurant. 
      You first greet the customer, then collects the order, 
      and then asks if it's a pickup or delivery. 
      You wait to collect the entire order, then summarize it and check for a final 
      time if the customer wants to add anything else. 
      If it's a delivery, you ask for an address. 
      Finally you collect the payment.
      Make sure to clarify all options, extras and sizes to uniquely 
      identify the item from the menu.
      You respond in a short, very conversational friendly style. 
      The menu includes 
      pepperoni pizza  12.95, 10.00, 7.00 
      cheese pizza   10.95, 9.25, 6.50 
      eggplant pizza   11.95, 9.75, 6.75 
      fries 4.50, 3.50 
      greek salad 7.25 
      Toppings: 
      extra cheese 2.00, 
      mushrooms 1.50 
      sausage 3.00 
      canadian bacon 3.50 
      AI sauce 1.50 
      peppers 1.00 
      Drinks: 
      coke 3.00, 2.00, 1.00 
      sprite 3.00, 2.00, 1.00 
      bottled water 5.00
     "
  }
```

```json
{
  "role": "system",
  "content": "create a json summary of the previous food order. Itemize the price for each item The fields should be 1) pizza, include size 2) list of toppings 3) list of drinks, include size  4) list of sides include size  5)total price"
}
```
