---
title: "KNB Notebook"
output: 
  html_document:
    keep_md: true
---
# Scope of the database
What are the measurements? Are there variables that are required for each data point? Try to explain in a programmatic way.

Since KNB has multiple datasets, it has info of all types of animals, including birds, fish, mammals, etc. Depending on the dataset, it has different types of variables and measurements. 

Take one dataset for example, which is the one I downloaded in the first notebook,
```{r}
river <- read.csv("~/Documents/nahis/knb-susquehanna-river-flow.csv")
str(river)
river
```
flow: cubic feet per second  
a: USGS gage number [google "1570500 usgs"](https://pubs.usgs.gov/of/2016/1038/ofr20161038.pdf)  


Another dataset
```{r}
mya <- read.csv("~/Documents/nahis/knb.92072.1.csv")
str(mya)
mya

# columns that have no NA's
table(factor(which(!is.na(mya), arr.ind=TRUE)[, 2]))
```


# Data Quality
I don't see any documentation on the standards. Units and abbreviations are quite vague. I have to go to the original site to refer to other similar datasets. Or google some unique data entries, such as IDs. 

But if it's about river, we can check the climate there and get a sense of rainfall and water stream, etc. Also for animal sizes, we can compare with their avarage sizes to detect possible outliers.

## Completeness
> requires that a particular column, element or class of data is populated and does not feature null values or values in place of nulls (e.g. N/As).

```{r}
which(is.na(river), arr.ind=TRUE)
which(is.na(mya), arr.ind=TRUE)
```

## Consistency
> Something that tests whether one fact is consistent with another e.g. gender and title in a CRM database.

We can check seasons and dates/datas and years. 

## Uniqueness
> Are all the entities or attributes within a dataset unique?

By now I haven't seen any duplicate attributes. Also, since I have data frames, I think all the attributes should be unique.

## Integrity
> Are all the relationships populated for a particular entity – for example its parent or child entities?

No. For crabs and fish, we only have their lengths. 

## Conformity
> Does the data conform to the right conventions and standards. For example a value may be correct but follow the wrong format or recognised standard.

The units are generally unclear. 

## Accuracy
> the hardest dimension to test for as this often requires some kind of manual checking by a Subject Matter Expert (SME).

# What are the variables that are most interesting to you?
> At some point you will need to refine the scope of your project. You likely cannot explore ALL the data. Are their questions about the that are particularly interesting to you? Questions can either be about the quality of the data or of biological significance.

Right now I'm thinking about how climate changes affect one species' living conditions. Or maybe just river flows? 
I think biological significance sounds pretty interesting but I'm not sure if there are a lot of things to be done. 


# Skills
> Reiterate what skills you particullarly interested in learning. Do you see a clear path from this database to level up on those skills?

If I do the quality of data, I think I can do something similar to what I did in a Data8 project, which is making a test set and compare the data with the set to determine the outliers. 
On the other hand, biological significance will lead me to a data visualization path, I think. I will compare different pairs of data attributes and find their relationships?

# Handle the data
Is there something that could be done to the data on the database side that would make your life easier when using this data? Do you wish it was in json over XML? Do you wish that there was a tool in Python that would connect to the database? Did you find the documentation incredibly hard to follow? What are some things you googled that helped you? What are the things you googled that had no answer but wish there was?

I'm actually able to read XML now using Atom because it colors different nodes. I also changed some settings to "soft wrap at preffered line length" and it makes xml way easier to read! I'm almost in love with it!  
Useful guide to limit line lengths in atom [here](https://stackoverflow.com/questions/49616864/limiting-line-length-in-atom)

