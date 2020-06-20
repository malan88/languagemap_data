# Language Map Data Repository

To see the program in action visit langmap.netlify.app

## About
This is the data for langmap.netlify.app. It is free for anyone to use or
modify.

This data was scraped from the [List of countries by spoken languages][0] on
Wikipedia. It was a horrifically badly formatted page, and I thus spent a good
deal of time aggregating it using Python, [gspread][1], the Google Drive/Sheets
API, and Google Sheets' `=importHTML()` function. It was by no means automated,
and I had to concatenate and label a lot of things by hand, specifically in
normalizing the status of each language within each country. Below is a series
of general rules of thumb I took as I went through the list.

## General Rules I Chose
- co-official, official or minority in [place] = regional
- spoken in <place> = regional
- co-official = official
- de facto, unofficial = de facto
- de facto, official = official
- minority everywhere, official somewhere = minority
- official minority = minority
- de facto/more than 50% = de facto
- widely used, not official = de facto

## Apologia

Mistakes were made. Get over it. You want it fixed? Do it yourself. This data is
free to be cloned and adjusted.

## Call to Action

I normalized the status codes to a mere 5.  I do not want more than there
already are. In fact, I would like to reduce the number. I understand that
languages are complex, but this project isn't meant to be a definitive resource,
it's just to give people a sense of how much of the world they can visit and
know the language in. Plus, I really don't know what the hell a naked
'unofficial' is. In general, that Wikipedia page is horribly sourced and
designed and if we can contribute back to it by renormalizing into a single
table it would be incredible, I'm just not sure if it would be welcome.

## How to Contribute
The original status descriptions of the languages on the Wikipedia page are
visible in original_non-normalized.csv. If you have a good reason to change the
status of a row or group of rows, please do so in langauges_final.csv and
explain the change in your commit/PR. The only sheet worth changing is that one
because it's the one from which I build the json file for langmap.netlify.app.


[0]: https://en.wikipedia.org/wiki/List_of_countries_by_spoken_languages
[1]: https://github.com/burnash/gspread