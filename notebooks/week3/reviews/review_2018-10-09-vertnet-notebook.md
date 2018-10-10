---
title: "Vertnet Notebook Review"
author: "Yuqing(Lyn) Lu"
date: "10/9/2018"
output: html_notebook
---
# Overall
Vertnet Notebook has really clear explanations about accessing the data and the package methods. I don't see any grammar or spelling issues.  

The interesting or useful part about this database is that since the data entries have the same variables, you only get one aggregated file for each search, so that you don't have to merge multiple files by yourself.

# Issues
- Yet the [link](http://portal.vertnet.org/search?q=FelidaeFamily) to "Felidae family" somehow doesn't work for me, which I think is because of the extra word "family"? When I searched "Felidae", I got some reasonable data and downloaded it via the link sent to my email.

- And I had trouble using the "rio" package. After loading the package `library("rio")`, I got the following errors:

> The following rio suggested packages are not installed: ‘clipr’, ‘csvy’, ‘feather’, ‘fst’, ‘readODS’, ‘rmatio’
> Use 'install_formats()' to install them

Following the error message and running `install_formats()` I was able to load the package.

# Suggestions
I found this [rvertnet package](https://github.com/ropensci/rvertnet), which allows you to search and download part of the data more efficiently. But you still have to provide email to get bigger data. 

Thanks for reading! :)
