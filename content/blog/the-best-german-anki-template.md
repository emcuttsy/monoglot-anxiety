---
title: "The best German Anki template. Probably. Automatic color-coding and cloze deletions"
description: "This free template automatically color-codes nouns based on gender, highlights irregular verbs, and even generates cloze deletions based on example sentences without an extra click. Supports images and audio."
author: ""
draft: false
date: 2021-02-28T15:05:45-07:00
tags: [german anki flashcards, german flashcards, german anki deck, anki template, anki for language learning, free german resources]
categories: [German, Anki]
ankidecks: [Card Templates]
comments: true
weight: 1
removeBlur: true
enableEmoji: false
images:
  - src: "https://monoglotanxiety.s3.us-east-2.amazonaws.com/2021/03/01/ankibanner.jpg"
  - alt: "A German flag and Anki logo intended to represent a German Anki deck"
  - stretch: ""
---

After almost a year of experimentation, I'm finally satisfied enough with my German Anki template to dare to think it might be useful for others. So in the spirit of Mads Mikkelsen advertising a [pretty mediocre Danish beer](https://www.youtube.com/watch?v=jEKLwFdntPs) as "probably the best beer in the world," I'll say that this is "probably the best German Anki template on the internet." **You can [download it for free](https://gum.co/saHJaW).**

Emphasis on probably.

This template **automatically generates cloze-deletions** from example sentences,  **determines the gender of nouns** and color-codes accordingly, and recognizes and **highlights irregular verbs**. It supports images and audio for both German words and example sentences, and has an inutitive input format that uses the same fields for all parts of speech—no special fields for nouns, verbs, etc. that are left blank all the time.

I released a similar template before, but it didn't work for verbs. This template works for *all* German words, and even has some extra features for verbs.

### The Anki template with example cards is free

Pay-what-you-want if you like, but otherwise just enjoy. 

<br>

<center>
    <script src="https://gumroad.com/js/gumroad.js"></script>
<a class="button gumroad-button" href="https://gum.co/saHJaW">Get the free deck</a>
</center>

<br>

If you notice any issues with the template or have comments, questions, ideas for improvements, or otherwise want to get in touch, please email me at hello@monoglotanxiety.com.

## About the template

The point of this German Anki template is to make it easier to make well-formatted German flashcards that help you learn better. That means making cloze deletions fast and easy, using an intuitive field setup for quick input, and color-coding nouns and verbs to help you notice and remember the important grammatical properties of these words.

### Features

* **Nouns automatically color-coded by gender**. The template determines a noun's gender automatically from its definite article (*der, die, or das*) and color-codes accordingly.
* **Irregular verb forms automatically highlighted**. The template highlights irregular verbs by predicting a set of theoretial "regular" conjugations and marking any that don't agree.
* **Cloze deletions automatically generated from example sentences**. My template uses a little script to predict different forms a word might appear in, search for these forms in the example sentence, and generate a faux cloze deletion by removing the correct word and replacing it with […]. This results in cards that look exactly like traditional clozes but doesn't require any extra clicks or additional note types.
* **Intuitive input with flexible fields that work for nouns, verbs, and everything else**. The same set of fields work for every word, regardless of whether it is a verb, noun, or something else. Field order mirrors the typical order in which words and their variants (i.e. plurals, conjugations) are provided in vocabulary lists.
* **Support for images and audio**. Cards work without images and audio, but media is added easily. Separate audio for words and example sentences is supported.

### Cards

* **Translation-to-German:** Front - translation, image. Back - German word, info (plural/conjugation), example sentence, audio of german word + front

![translation to german card](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2021/03/01/monoglotanxiety-3.jpg)

* **German-to-Translation:** Front - German word, info (plural/conjugation), example sentence, image, audio of German word. Back - translation + front

![german to translation card](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2021/03/01/monoglotanxiety-2.jpg)

* **Auto-close:** Front - auto-cloze, translation, image. Back - auto-cloze answer, audio of example sentence, German word, info (plural/conjugation) + front

![auto cloze card](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2021/03/01/monoglotanxiety-1.jpg)

I hope this card format makes at least one aspect of your German study routine a bit easier. Flashcards are a super helpful tool, but time spent messing with formatting and making extra cloze deletion cards takes up time that could be better spent actually learning German.

<hr>

## How-to guide

**There are example cards in the deck package that demonstrate how to use the template** for nouns (plural-only and normal), verbs, and everything else. Follow the input format demonstrated in those cards and you'll be golden. But just in case something isn't clear, you can read the guidelines below. Shoot me an email at hello@monoglotanxiety.com if you're confused or if you notice a bug.

At minimum, you need input for **German** and **Translation**. Auto-cloze rand color-coding require both **Example** and **Info** (for nouns and verbs) to work properly, and no auto-cloze card is attempted if no example sentence is provided.

{{<note title="The 'info' field">}}

German nouns, verbs, and other words follow different sets of grammatical rules. This template works for all German words because it  can determine what kind of word it's dealing with and respond accordingly. **The "info" field contains grammatical information necessary for the auto-cloze and color-coding functions.** For  verbs, that means conjugations. For nouns, that means the plural form or a note indicating plural-only nouns.

This might sound a bit complicated, but it's intuitive once you see it in action—and a lot nicer to deal with than a bunch of noun- or verb-specific fields that get left empty all the time. Just be sure to look at the examples and take note of the simple rules below to avoid getting frustrated. **Pay special attention to how to use the "info" field for verbs and nouns.**

{{</note>}}

* **german:** the German word. Nouns should be preceeded by their definite article (*der, die,* or *das*) and verbs should be in the infinitive. For reflexive verbs, add *sich* before the infinitive. 
  * Examples: *"der Hund", "die Maus", "sprechen", "sich wundern", "abfahren", "rot"*
* **info:** additional forms/information, usually only relevant for nouns and verbs.
  *  **Nouns**: the plural preceeded by *die*. If the noun is plural-only write one of p, plural, plural only, or plural-only. For nouns with no plural, leave blank. Examples: *die Hunde, die Mäuse, plural,  [no input]*
  * **Verbs**: provide the 3rd person present, preterite, and past perfect conjugations in that order, with ", " separating the elements. Provide the auxilliary verb. Examples: 
    "*spricht, sprach, hat gesprochen*", "*wundert sich, wunderte sich, hat sich gewundert*", "*fährt ab, fuhr ab, ist abgefahren*"
  * **Other**: leave blank or use for custom information.
* **translation**: the translation
* **example:** example sentence. Try to avoid using words that start with the same stem as the word you're quizzing to avoid confusing the auto-cloze (e.x. don't use "Meine Freunde freuen sich…"  as an example for "freuen" since Freunde will look like a version of freuen to the auto-cloze script).
* **register:** extra field for notes on usage/register. Shown on all card fronts, so be careful with spoilers. Examples: *"wissenschaftlich", "österreichisch", "gehoben"*
* **image:** an image. If you use attribution text for the image, include it below the picture and it will be displayed in small text beneath the image.
* **german audio:** audio file for the german word.
* **example audio:** audio file for the example sentence. 

### Known issues

Tell me if you find more or if you come up with a fix! Email hello@monoglotanxiety.com

* Auto-cloze mistakes words that begin with verb stems for a version of the verb, and deletes them. Example: Using "Meine Freunde meinen, dass Hunde gute Haustiere sind." as an example for "meinen" will result in "[…] Freunde […], dass Hunde gute Haustiere sind".
  * Work-around: use a different example sentence. 
* Certain adjectives that change stem aren't recognized by auto-cloze. Example: teuer –> teuren is not recognized correctly because the e and r switch places.
  * Work-around: use example sentences that take the base form of these adjectives.

<br>

<center>
    <script src="https://gumroad.com/js/gumroad.js"></script>
<a class="button gumroad-button" href="https://gum.co/saHJaW">Get the free deck</a>
</center>

<br>

