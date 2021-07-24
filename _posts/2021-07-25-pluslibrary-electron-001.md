---
date: 2021-07-25 00:00:01+0800
layout: post
slug: "pluslibrary-electron-001"
title: "plusLibrary-electron #001"
description: "A post about the project, and what's being done"
tags: plusLib,programming
---
## {{page.description}}

hi. i plan to consistently do this kind of blog posting to log down the progress of plusLibrary-electron.
it's more on self-reflection though, but let's get to it.

---

## What is plusLibrary?

plusLibrary is a spreadsheet project made to track as much information from my Steam Library.
There are tools like [SteamDB's Calculator](https://steamdb.info/calculator/), but the data it could give you was more or less limited to what Steam's WebAPI could pull.

...so I made plusLibrary to be able to **track down user-inputted statistics**, such as **paid cost, a rating system, and a completion indicator**. <!--more-->

---

[![001_01](\assets\images\plusLib\001_1.png)](\assets\images\plusLib\001_1.png)

plusLibrary is split into 4 main sections:

- **Overview**

This is pretty much the prettified view; a wall of information that I'll just look at most of the time. It's just showing a reference of the data in MyLibrary.

- **MyLibrary**

Data is was processed (spun through lots of functions) from DataProcessing and placed here. This is where I input user-inputted stuff.

- **DataProcessing**

This is the raw numbers that are slapped here straight from Steam's API -- numbers like playtime and achievement numbers. Statistics are periodically pulled through AppScript.

- **PlayerStats**

This is where I store important things like the API key and SteamID, as well as some general numbers like account age/creation date, as well as game count, XP numbers, etc. There's some counters here as well.

There's additional things as well:

- **Backup**

For some reason, sometimes pulling the API data fails and that automatically causes a catastrophic chain reaction to delete all the game entries in the spreadsheet. I made this to at least save the user-inputted data.

- **ExceptionList**

Just yesterday (as of writing this), I learned that Steam's WebAPI was updated(?) to allow unvetted store apps as an option (basically, those games that have a label called "Profile Features Limited"). ExceptionList was originally supposed to be user-inputted Steam games since the WebAPI originally didn't have a way to list them, so that those would also be in the spreadsheet.

---

That's the basic gist of how plusLibrary operates. You can view the sheets [here](https://docs.google.com/spreadsheets/d/13VnHkpbFelfV0vy9cD1WzceWGk1zwlsq3ZMoxL4Ttuc/edit?usp=sharing) and the AppScript source code [here](https://github.com/nzo-e/plusLibrary), but as a disclaimer: I've not done documentation for those because I made those mainly for my personal gain, and not with the intention of making it sharable.

Now we talk about the -electron part.

---

## The -electron part

The main purpose of the electron project is to **replicate the functionality of the original project**, into something that **can be distributed to other people**.

Why an electron project?:

- **.gs is basically .js**

...was my initial thinking; I already had the code, and I  more or less just had to adjust the code to work in an electron environment.

- **I wanted to learn something relatively new**

The last time I touched web development was back in 2017, in year 1 of my game development diploma course. Wouldn't be bad to touch up on something I haven't really touched on, right?

This wouldn't be so bad, right?

*Right..?*

---

## The progress so far

The biggest roadblocks were in figuring out how electron worked, and how to package it into a usable application. The biggest part was getting electron-forge to work properly, I didn't (and still don't) know how to debug error messages.

But after clearing that hurdle, I went ahead and did some testing on a debug page.

[![001_02](\assets\images\plusLib\001_2.png)](\assets\images\plusLib\001_2.png)

A debug page, buttons to trigger functions, and the console to log everything.

So far, it's working fine. I have buttons to help with:

- Saving settings
- Pulling from the SteamAPI
- Manipulating a database to store and update our game data

*Please don't look at the source code, that shit is a nightmare.*

Moving forward, until next week, the main priority is to:

- Render out the game data into the webpage
- A way to edit in user-inputted data

Anyways, thanks for reading. Hopefully I'll see myself writing in next week.

nzoe (enzo).
