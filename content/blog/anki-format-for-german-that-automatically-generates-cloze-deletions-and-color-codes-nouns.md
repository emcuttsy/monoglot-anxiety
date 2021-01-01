---
title: "Anki template for German that automatically generates cloze deletions and color-codes nouns"
description: "Using the magic of German grammar, this anki template automatically color-codes nouns by gender and generates cloze deletions without extra clicks or note types—just enter the word and an example sentence."
author: "Anxious Monoglot"
draft: false
date: 2020-12-31T15:20:02-07:00
tags: [anki card template, german anki template, anki, language learning]
categories: [German, Anki, Language Learning]
ankidecks: [Card Templates]
comments: true
removeBlur: false
enableEmoji: true
images:
  - src: "img/2020/12/card3.jpg"
  - alt: "Duolingo German golden owl trophy with a crack"
  - stretch: ""
---

One of my major frustrations with Anki is the stiffness of cloze-formatted cards. They just don't play nice with basic card types. So while I often want to incorperate cloze deletions into my decks, making seperate notes for clozes of my example sentences is simply beyond my effort tolerance.  So instead of spending an extra 30sec/card, I did the *clearly* easier thing and spent a week figuring out how to get basic cards to automatically make cloze deletions based on example sentences. 

Finally, an aspect of Anki that is willing to accomodate my laziness!

You can [download my Anki template for German for pay-what-you-want](https://gum.co/monoglotanxiety-autocloze-nouns-etc) (so probably free) or from [Ankiweb](https://ankiweb.net/shared/info/1483890412). One thing—thanks to German's *fun* grammar, the auto-cloze feature doesn't work for verbs (yet, [see my note at the bottom](#no-verbs-yet-but-stay-tuned)). 

If you do test out the format, I'd love to hear from you—especially if something went wrong. I'm happy and eager to fix any bugs you might find. Happy Anki-ing

## Features

### Automatically-generated cloze deletions generated based on the example sentence

Anki basic cards and cloze deletion note types do not play nice. Usually, if you wanted to make a cloze-deletion for an example sentence from one of your basic note types, you'd need to either a) make a whole separate note for the cloze deletion or b) manually make "fake" cloze deletions, which requires you to create aseparate fields for the complete sentence and the "clozed" version with your word removed and replaced a blank or other characters.

That's a drag, especially since cloze-deletions are a great way to learn words in context. 

**This card format makes generating cloze deletions painless—just provide an example sentence containing your word and a script in the template takes care of the rest!** These "auto-cloze" cards aren't true Anki cloze deletions, so they don't require you to use a different note type for your clozes and basic cards. Auto-cloze cards are associated with the same Basic type note as the German-to-translation and translation-to-German cards. Thanks to a bit of grammar magic under the hood, **this even works if your word appears in the example in an inflected form.** 

### Nouns color-coded by gender based on article

Nouns are automatically recognized by the card template and color-coded according to gender based on their preceeding article (der/die/das). Plural-only nouns are also color-coded—just write *p*, *plural*, *plural only*, or *plural-only* in the "Plural" field to indicate that a noun is plural-only. See [the how-to](#how-to) for more on plural-only nouns. 

If you don't like my color choices, you can change the colors of the `masculine`, `feminine`, `neuter`, and `plural-only`  CSS classes in the "Styling (shared between cards)" in the card template window.

### Intuitive input format 

In my early days of exploring the wonders of custom Anki formats, I made the mistake of adding so many specific fields to my cards. One format I used for German had more than 8 fields at one point, with separate places to input noun articles, gender, plural forms, verb conjugations, and and and. It basically made the format unusable since I'd always make mistakes inputting information into all those fields. A lot of that is because Anki's built in conditional replacement function only works based on field presence/absence. But 8 months later I have [a solution to that problem](/blog/conditional-formatting-based-on-field-content-for-anki-flashcards/) and now the field bloat is finally over. 

I really wanted to keep things intuitive for these cards. **The order of fields and expected format for input aligns with how German vocabulary is usually shared in list—i.e. article + noun, plural, translation**. And conditional formatting behind the scenes allows the same fields to be re-used for different kinds of words without causing any trouble. No separate fields for nouns and non-nouns or anything like that!

<br>

<center>

<script src="https://gumroad.com/js/gumroad.js"></script>
<a class="gumroad-button" href="https://gum.co/TOguD" target="_blank">Get the template for free! (or pay what you want)</a>

You can also [download the template from AnkiWeb](https://ankiweb.net/shared/info/1483890412).

</center>

<br>

## Example

Here's a quick example of how nicely the cards work. Below are a screnshots of what I typed into the input window and the cards generated by the template:

![anki input](/img/2020/12/fieldpreview.png)

### Card 1: translation to German

![translation-to-German anki card](/img/2020/12/card1.jpg)

### Card 2: German to translation

![translation-to-German anki card](/img/2020/12/card2.jpg)

### Card 3: Auto-cloze

![translation-to-German anki card](/img/2020/12/card3.jpg)

## How-to

Hopefully the uses for the fields are intuitive. But there are a few things to keep in mind to make sure that the auto-cloze and color-coding features works correctly. Here's a list of what you can put in each field:

**Field 1: German**

* a noun preceeded by its der/die/das article (*die Maus* :white_check_mark: , *Maus* :x:)
* an adjective, conjunction, or any other word that is…
* **NOT** a verb. Auto-cloze doesn't work for verbs (see the end note).

**Field 2: Plural**

* blank if the word in Field 1 is a noun without a plural form or if it is not a noun
* the plural form of the noun in Field 1, preceeding"die" optional (*die Mäuse* :white_check_mark: , *Mäuse* :white_check_mark:)
* one of *p*, *plural only*, *plural-only*, or *plural* if the word in Field 1 is a noun without a singular form. This is important, since <u>if this information is omitted your plural-only noun will be color-coded as a feminine noun</u>. 

**Field 3: Translation**: A translation of the German word into a language you already know

**Field 4: Example sentence**: An example sentence in German containing the word in Field 1. And here's the magic bit: <u>your word can appear in an inflected form, and auto-cloze will still work!</u> (*Ich sehe <u>die Maus*</u> :white_check_mark:, *Ich sehe <u>die Mäuse*</u> :white_check_mark: ). Do *not* treat this field like a cloze field (*Ich sehe die Maus* :white_check_mark:, *Ich sehe {{c1:die Maus}}* :x: ). The cloze is done automatically by a script in the card template.

**Field 5: Image [optional]**: An image (or multiple images) that relates to the word in Field 1.

You could easily add fields for audio or translations of your example sentences, but I wanted to keep things minimal to avoid field-bloat. If you have requests for new features/fields, just let me know in the comments!

---

## No verbs yet, but stay tuned

Even for regular German verbs, the grammatical rules governing conjugation are much more complicated than for noun declension and adjective agreement. So making an auto-cloze format for verbs was a lot harder than making one for nouns, etc.

I have a working auto-cloze template for verbs now that can also detect and highlight irregular verbs when the traditional 3-tense conjugation is provided (i.e. denkt, dachte, hat gedacht). However, I want to test it a bit more before making it available since its possible there are bugs I haven't caught. And since getting verbs to work has been a *lot* of work, I'll probably end up asking for a few bucks in exchange for the auto-cloze-everything-and-automatically-highlight-irregular-verbs card format.

Thanks for reading, and let me know how the template works for you!