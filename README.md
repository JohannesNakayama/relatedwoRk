# Comprehensive Literature Review Sheet

When reviewing literature / related work for a scientific paper, organizing one's notes on the different readings can be a chore. This project provides an RMarkdown template for comprehensive literature reviews to help scientist organize their readings in a comprehensive and tidy way.  

The questions in the template are adopted from William G. Griswold's great guide on how to read an engineering paper (http://cseweb.ucsd.edu/~wgg/CSE210/howtoread.html). Feel free to customize them to fit your needs when reviewing related work.  

(I recommend using RStudio for the further steps)

## How to install

Just execute this line of code in the RStudio console:

`devtools::install_github("JohannesNakayama/relatedwoRk")`

## How to use

Open a new RMarkdown file by following these steps:

File > New File > RMarkdown

In the dialogue, choose "From Template". In the list of possible templates, there should be the option `literature review sheet`. Choose this option and the template will open.

## Suggested Workflow

Have the template open while doing your reading. If you find something worth summarising, fill in the fields on this template (title, author(s), year) and take notes on the template while reading the material. 

The `setup` code chunk contains a call to the function `GetBibEntryWithDOI()` from the R package `RefManageR`. Insert the DOI of your source like this:  

```
RefManageR::toBiblatex(
  RefManageR::GetBibEntryWithDOI(
    doi = "<insert doi here>", 
    temp.file = "tmp.bib", 
    delete.file = TRUE
  ) 
)
```

When you execute it in the RMarkdown sheet, it will generate a bibtex entry for your source. You can copy and paste it into the `bibtex` code chunk. This will display the bibtex entry in the final pdf file. Remember to comment out the `GetBibEntryWithDOI()` call after you obtained the bibtex entry.

NOTE: You should think of a convention for naming your review documents so that you can query them later. Here is a suggestion:

* three or less authors: `<authors' last names>_<year>_<title>.pdf`
* more than three authors: `<first author's last name et al.>_<year>_<title>.pdf`




