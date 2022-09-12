+++
author = "Elise Cutts"
categories = []
date = ""
description = "You can use iOS automations to automatically start and stop time tracking apps like Toggl when you open and close language learning apps — and much more!"
draft = true
enableComments = true
images = []
sidebar = "right"
subtitle = "You can use iOS automations to automatically start and stop time tracking apps like Toggl when you open and close language learning apps — and much more!"
summary = "You can use iOS automations to automatically start and stop time tracking apps like Toggl when you open and close language learning apps — and much more!"
tags = []
title = "How to automatically track language learning time using iOS automations"
type = "featured"

+++
I'm often asked how much time I spend on language learning. This is a good question, especially since I learn through comprehensible input and time is undeniably the most important of the rather few levers one can really manipulate in an input-based study "strategy."

Unfortunately, I don't really have any idea. People who ask me about the time I spend on language learning usually end up receiving some totally unhelpful answer like "a lot."

It's not that I wouldn't like to know — I'm just quite bad at tracking time.

The problem isn't that there aren't good tools for this — these days there are plenty of great services built to help record every second you spend on every task imaginable. Plenty of people in the language learning community and beyond use these apps to catalogue their time with intimidating accuracy.

So no, the problem isn't the tools. The problem is bothering to actually use the tools.

I'm definitely on the chaotic side of the [D&D alignment chart](https://dungeonsdragons.fandom.com/wiki/Alignment) and — despite my desperate wish otherwise — am unfortunately rather allergic to organization. The only reason I can learn languages successfully is because languages are one of the few magical things in this world that don't require focused, structured work to get good at.

Needless to say, it isn't natural for me to start and stop a time tracker whenever I do anything.

Thankfully, internet strangers are far more clever than I am and someone figured out a solution that makes it practically effortless to track time, even if you're a disorganized mess like me: iOS automations and shortcuts.

**This post walks through how to use shortcuts to track language learning using Toggl** — but you can use whatever tracker you'd like so long as it is compatible with shortcuts. There's a bit of a learning curve, but don't worry. It's not too bad and I've already made plenty of mistakes testing things out so you don't have to yourself.

## Use iOS Shortcuts and Automations to automatically operate a time-tracking app on your phone

You can set up iOS automations to automatically start and stop your time tracking app when you open and close apps that you use to learn languages. I use [Toggl](https://toggl.com) as my time tracker, but there are other trackers like [Clockify](https://clockify.me/free-toggl-alternative) and [Polylogger](https://polylogger.com/auth/login), which was built specifically for language learners. I can't promise that other apps will work the same way as Toggl but it should be possible to use them, too.

Shortcuts are no-code programs that let you automate repetitive tasks on your iPhone. Automations are shortcuts that run when certain events or "triggers" occur — like opening a specific app. You can run shortcuts from within automations.

For instance, you could create an automation to automatically start a Toggl timer for Duolingo when you open the Duolingo app. Using another automation, you could automatically stop the timer once you close Duolingo.

It's that simple! Your phone will do the hard work of remembering to run your shortcut for you.

Credit where credit is due: thank you to [Tanya](https://twitter.com/botanechka) on Twitter for the idea to use iOS automations to operate a time tracking app.

{{< tweet "1564938702115184640" >}}

### Example: Automatically track time spent listening to podcasts in your target language

I listen to a lot of podcasts for language learning. Here's an example of how to set up an automation to track your time spent listening to podcasts in Toggl. It only works for one language — see below if you're learning more than one.

First, open the Shortcuts app and create a new Automation. Set the automation to trigger when an app is opened and select your podcast app. I used Pocket Casts for this example.

<center>

![](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2022/09/toggl1.png)

</center>

Then add a Toggl "Start Time Entry" action and set the description and project. In this example, the description is "Podcasts" and the project is "German," because I'm learning German. You can also set a task for the time entry, assign it tags, and designate it as billable or non-billable by clicking the little blue arrow next to the project field.

You can then decide whether you want the automation to run automatically or to ask you first before running.

<center>

![](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2022/09/toggl2.png)

</center>

## What if you're learning multiple languages?

If you're learing more than one language, you can add a step to your iOS automations that prompts you to select the language you'd like to track from a dropdown menu.

<center>

![](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2022/09/dropdown.png)

</center>

Use the "Choose from Menu" action to set up your dropdown menu. Make an option for each language you'd like to track. Then add appropriate time tracking actions for each of the language menu options. For instance, if I select "German" from the menu, my shortcut starts a Toggl timer for "Podcasts" in the "German" project.

<center>

![](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2022/09/dropdownshortcut.png)

</center>

If you use automations to track time in more than one app, it might be worth setting up a shortcut for choosing a language and starting an appropriate Toggl timer that you can reuse in your automations. This will save you time if you ever want to add or remove a language from your dropdown menu — instead of updating every automation, you can simply update the shared shortcut once.

See the example at the end of this post to get an idea of how this can work.

Using a shared Shortcut for selecting your language also opens up some fun options for setting up other kinds of automations and shortcuts that help with time tracking.

For instance, I created a button on my phone's Home Screen that makes it easier to track language learning activities that don't have their own app. When I tap the button, I'm prompted to choose a language (using the "Choose language" Shortcut) and then select an activity from a dropdown list. The Shortcut starts an appropriate time entry in Toggl and I use another, adjacent button to easily stop tracking once I finish.

<center>

![](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2022/09/button0.png)![](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2022/09/button1.png)</center>

## Tips for Toggl-based shortcuts

Toggl is one of the most popular time tracking apps in the language learning community and it plays nice with shortcut actions. But it also has some quirks that can make it tricky to set up more sophisticated shortcuts and automations.

### Choose from List vs Choose from Menu

These two similar actions aren't strictly Toggl-related but they work differently in ways that matter for using dropdown menus with your Toggl-based time tracking automations.

**Choose from List** prompts you to select from a list of options and passes the selection to actions downstream as a "text" variable. Attention! You need to set up a "List" object first before you can use it.* This confused me at first.

**Choose from Menu** prompt you select from a list of options and runs different actions depending on the option you chose. It's sort of like an input followed by an "if" statement. It _doesn't_ pass the selected option as text to a variable that can be used downstream.

### The Toggl Track iOS Shortcut actions

Toggl has four iOS shortcut actions: Start Time Entry, Stop Time Entry, Continue Last Time Entry, and Check Reports.

**Start Time Entry** starts a new timer in Toggl. It takes two required inputs: "Description" (text) and "Project" (Toggl project). There are optional inputs for "Task" (Toggl project task) and "Tags" (Toggl tags) and it's possible to designate timers as billable or non-billable time.

**Stop Time Entry** stops the current Toggl timer.

**Continue Time Entry** re-starts the last Toggl timer you stopped.

**Check Reports** opens Toggl and shows a summary report for a given period (day, month, year, etc.).

### Passing variables to the Toggl Start Time Entry action

The Toggl Start Time Entry action cannot accept text inputs to "Project," "Task," or "Tags." These fields can only be filled by selecting projects, tasks, or tags from lists your phone generates by checking your Toggl workspace.

Confused? In practice, this means that you cannot use "Choose from List" to choose a language and pass its name to the "Project," "Task," or "Tags" fields in the Toggl action. You need to use the "Choose from Menu" action and set up customized Toggl timer actions to run based on the selections.

The "Description" field does accept text inputs, however. This means that you can use the "Choose from List" action to set the names of your Toggl tasks.

{{<notice note "Should automations run automatically or ask first?">}}

If you tell your automation to ask before running, you'll get a push notification every time your automation is triggered that you can tap to run it.

This doesn't actually gunk up the "automatic" feel of the automations that much, and I recommend having certain automations ask before running.

For podcast apps, I think it makes sense to ask before starting or stopping a Toggl timer since we often open other apps while listening to podcasts. But for apps like Duolingo that we can only actively use while they're open, it's probably fine to just let automations run on their own.

{{</ notice >}}

### Example: Universal "Language Dropdown Menu" Shortcut for Toggl-Based Time Tracking Automations

This is all pretty abstract, so here's an example of how this can work. I set up a universal "Language Dropdown Menu" shortcut for my Toggl-based time tracking automations.

Here's what it looks like:

![](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2022/09/universal-menu.png)

When it runs, it just opens up a dropdown menu of languages and then starts the appropriate Toggl Timer based on whatever activity it receives as input to the description field (i.e., Video, Formal Study, etc.)

This saves me time because I don't need to set up dropdown menus for every shortcut I create — my automations tracking Duolingo, Speakly, and my podcast app all share the same same dropdown menu shortcut.

{{<notice note "Shortcut inputs and automations running shortcuts">}}

Automations can run shortcuts and shortcuts can take input from automations and other shortcuts. To give your shortcut an input from another shortcut or automation, use "Shortcut Input" as a variable to fill some field in your automation and select "What's Onscreen" as the source of input. It's a weird name but it just means "whatever the other app you called this shortcut from passes into it"

{{</ notice >}}

My Toggl tracking for language learning is rather basic and only has two organizational layers — Languages (projects) and categories like Podcasts, Lessons, etc., which I set as descriptions. Toggl lets you easily search by description so I'm just consistent in my naming scheme. You'll need to set up a more sophisticated dropdown shortcut with a lot of conditional statements if you use a more complicated system with tags and tasks.

## Use shortcuts to more easily track language learning that doesn't involve your phone

Once you set them up, automations and shortcuts make it practically effortless to log the time you spend using your phone for language learning — and they can make it easier to track time you don't spend on your phone, too.

### Example: Track Language Learning button

Using shortcuts, I created a button to quickly track time spent on different types of language learning activities.

Click here to see the shortcut.

When I tap the button, it opens a dropdown menu of the different types of language learning activities I track — podcasts, video, lessons, exchange, etc. Once I select one of the options, I'm shown a dropdown menu of languages. An appropriate Toggl timer starts automatically after I've made my selections.

Having a Toggl widget on my Home Screen right next to my language tracking button is helpful to make sure I don't forget to stop the timer.

## Example Toggl Tracker Shortcuts

Here are a few example shortcuts showing different ways to automatically track time spent on language learning. Let me know if you find any errors!

* [Duolingo tracker with language dropdown](https://www.icloud.com/shortcuts/654e3b686bea4e33a68a36776f6301a8)
  * Automation: When Duolingo opened, run this shortcut

Using shared language dropdown + start Toggl tracker shortcut

* [Shared language dropdown + start Toggl timer shortcut](https://www.icloud.com/shortcuts/2de7d367632c4a46b5097e4876c07897)
* [Duolingo tracker using shared language dropdown menu](https://www.icloud.com/shortcuts/cc59c21e6fdd43a19a3285982773f16f)
  * Automation: when Duolingo opened, run this shortcut
* [My personal podcast tracker with option for listening to English podcasts](https://www.icloud.com/shortcuts/4f46ae4298f9404ea2c79a3ebce4502d)
  * Automation: when Snipd (podcast player) opened, run this shortcut

Remember to set up automations to stop your time tracker timers when you close apps!

## How do you track your language learning time? If at all?

How do you track your time spent on language learning? I'm finding that this system works great for me — great as in I _am actually using it halfway effectively_. 

Do you have any fun shortcuts that help you track your time? Do you use an app other than Toggl? I'd love to hear about what you do differently — and quite probably better — than me!

And finally, in case you're curious... here is my tracked time for the last 3 days. I'm taking a German Intensive Course right now which is why I have 3 hours of lessons in the mix (today is Monday). Podcast hours can really rack up quickly.

<center>

![](https://monoglotanxiety.s3.us-east-2.amazonaws.com/2022/09/Screen Shot 2022-09-12 at 16.23.48.png)</center>