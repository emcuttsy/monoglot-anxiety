---
title: "Conditional formatting based on field content for Anki flashcards"
description: "Change card styling and text in Anki based on the content of your note fields, not just whether they're empty or not empty"
author: ""
draft: false
date: 2020-12-12T10:06:21-07:00
tags: [german anki flashcards, german flashcards, anki template, anki tips, anki for language learning]
categories: ["Anki"]
comments: true
removeBlur: true
featured: "2020/12/conditional-formatting-banner.jpg"
featuredalt: "Conditionally format Anki cards based on field content"
featuredstretch: ""

---

Anki allows conditoinal formatting based on whether or not fields are empty, but you’ll need to use a bit of code for conditional formatting in Anki based on field content. Luckily, it’s not that hard, and using this trick you can conditionally display text as well. I use it to color-code my German flashcards by noun gender without having to do everything by hand.

Out-of-the-box, Anki supports "[conditional replacement](https://docs.ankiweb.net/#/templates/generation?id=conditional-replacement)," which changes what gets rendered on a card is based on whether or not fields are empty. This is how it works:

``` 
Shown always

{{#Field}}
Shown only if Field is not empty
{{/Field}}

{{^Field}}
Shown only if Field is empty
{{/Field}}

Shown always
```

That's useful, but it has limitations.  

If I wanted to use conditional replacement to color-code my German cards by gender, I would have needed to create different fields for the masculine, feminine, and neuter[^1] definite articles and be careful to only fill in one of those 3 fields as I made my cards. And that's maybe even more of a pain in the butt than going through and color-coding everything by hand.

Luckily, there's a way to pull off content-based conditional formatting even if it isn't baked into Anki.  The solution involves a bit of CSS and Javascript, but trust me, it's not too painful (definitely less painful than hand-formatting everything) and you can mostly copy-and-paste the templates below.

*Credit where credit is due: I didn't come up with this myself. Look hard enough on Anki forums and you'll find the answer (I found it [here](https://anki.tenderapp.com/discussions/ankidesktop/21132-conditional-formatting-based-on-deck#comment_41634514)). But I wanted to save other code-illiterates the hours it took me to figure out how to make this work by going into a bit more detail and providing a concrete example.*

## Changing card style and displaying different text based on field content

The way this works is by using Javascript to change the CSS styling of some part of your card based on field content. You can also change what text gets displayed based on field contents as well. This card template shows how to do both:

**Card Template (front and/or back):**

```
Normal content

<span id = 'conditional_style'>
    Conditionally styled content
</span>

<!-- conditional text-->
<span id = 'conditional_text'></span>

<script>
<!-- conditional style-->	
    if ('{{Field}}' == 'condition'){
      document.getElementByID('conditional_style').classList.add('condition')
    };

<!-- conditional text-->
    if('{{Field}}' == 'condition'){
      document.getElementById('conditional_text').innerHTML = 'conditional text'
    };
</script>
```

**Styling (shared between cards):**

```
.card{
/* card style */
}

.condition{
   /* condition1 style */
}
```

Let's break this down:

The condition this card checks for is whether the text in field "Field" (creative name, right?) is exactly the word "condition."  If the condition is met, the `conditional style` span is styled by the CSS class `condition` (defined in the Styling box) and the `conditional_text` span is replaced by "conditional text." If the condition isn't met, then everything is styled by the `card` CSS class and no conditional text is shown.

If you're confused about how the JavaScript between the `<script>` tags works, check out [this page on conditionals in JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals) and these on [finding elements by their id](https://www.w3schools.com/jsref/met_document_getelementbyid.asp), [changing their CSS class](https://www.w3schools.com/jsref/prop_element_classlist.asp), and [replacing their internal HTML](https://www.w3schools.com/js/js_htmldom_html.asp). The nice thing is that once you get how this works, it's easy to adapt the basic idea to do whatever specific task you might have in mind. For instance, it'd be easy to condition your cards on other true-false conditions, like [whether a field includes a certain word](https://www.w3schools.com/jsref/jsref_includes.asp) (rather than precisely equalling it). 

You can also embed conditional text within a conditionally styled span. Which is exactly how my German noun flashcards work.

## Example: color-colding German articles by gender

That's all pretty abstract, so instead of ending there I wanted to quickly go through how my German flashcards work. I've only shown the template for the front of the German-to-English card since the code works the same wherever you paste it and this post is getting long enough already. [You can download my deck from Ankiweb](https://ankiweb.net/shared/info/1877324510) if you want to take a look at the card templates more closely (but it's a work in progress and the templates are messier than the cleaned-up version I show here. You've been warned!).

**Fields[^2]:** German, Gender, Plural, English, Example, Images

In the Gender field, I use "m" for masculine, "f" for feminine, and "n" for neuter nouns. I also sometimes use "p," which stands for "plural-only" to distinguish feminine from plural nouns when there's no singular form.

**Card Front:**

```
<big>
    <span id="gender_color">
        <span id="article"></span>
    </span>
    {{German}}
</big>

<small>{{Plural}}</small>

<br>
{{Example}}
<br>
{{Images}}

<script>
    if ("{{Gender}}" == "m") {
        document.getElementById("gender_color").classList.add('m')
        document.getElementById("article").innerHTML= 'der'
    }
    
    else if ("{{Gender}}" == "f") {
        document.getElementById("gender_color").classList.add('f')
        document.getElementById("article").innerHTML = 'die'
    }

    else if ("{{Gender}}" == "n") {
        document.getElementById("gender_color").classList.add('n')
        document.getElementById("article").innerHTML = 'das'
    }

    else if ("{{Gender}}" == "p") {
        document.getElementById("gender_color").classList.add('p')
        document.getElementById("article").innerHTML = 'die'
    };
</script>
```

**Styling (shared between cards):**

```
.card {
 font-family: arial;
 font-size: 40px;
 text-align: center;
 color: black;
 background-color: white;
}

.m {
color: royalblue;
}

.f {
color: palevioletred;
}

.n{
color: goldenrod
}

.p{
color: black
}
```

The result? Some nicely color-coded cards that I didn't need to color-code myself. And the best part is that this will automatically work on any new cards of this note type as well, which is great for me since I tend to mass-import cards from spreadsheets of vocabulary.

![Image](/img/2020/12/conditional-formatting-example-cards.png)

For anyone wondering, yes those are my cats. Their names are Hubble and Chandra. The dog (Jule) is my boyfriend's.

Happy flashcarding!

[^1]: I'd also need a field for plural nouns. Some German nouns only ever take the plural definite article "die," which is identical in the nominative case to the feminine article. I color-code plural nouns differently as well, and this overlap of "die" is one of the main reasons I don't conditionally format on an article field containing one of "der" "die" or "das" but rather on a gender/plural field containing one of "m" "n" "f" and "p". 
[^2]: These aren't exactly the names of the fields I use, since I store more than one definition for each word on my cards. I simplified things for clarity.