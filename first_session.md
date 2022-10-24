*This is the first session's notes. If you want the second session, go back to [https://github.com/elsherbini/kwonlab_R_workshop_20221017]*

## Intro to R and R studio

Today we’re going to get started with R and Rstudio. By the end of
today’s session, you should know how to :

-   Change options in Rstudio
-   Create an Rmarkdown document
-   Use different types of data in R
-   Read in tabular data like a csv file
-   Make quick summaries of dataframes
-   Create new columns in dataframes

### 1. Download today’s materials

**Do This:**  
- Go to <https://github.com/elsherbini/kwonlab_R_workshop_20221017>  
- Click on the green “Code” button and “Download Zip”  
- Move the zip file somewhere sensible and unzip it

### 2. What is R and Rstudio?

R is a programming language, which means you can write programs as text
that adheres to a syntax and R will interpret your program into
instructions for the computer. R was released in 1995, but it was based
on an older language from 1976. Because it is so old, there is sometimes
ugly syntax or several ways to do the same thing, which is confusing.

Rstudio is the name for this code editor, and also the team who makes
the `tidyverse` set of packages. These packages try to make using R more
powerful and less confusing for working with data.

#### changing options

**Do This:**  
- Open up RStudio - Got to Tools -&gt; Global Options . - Under
Workspace, uncheck “Restore .RData into workspace on startup” - Change
“Save workspace to .RData on exit” to “Never” - Switch to the Appearance
pane on the left, and look at different themes. - Try Dracula, Cobalt,
and Tomorrow Night 80s. Pick any theme you want and git “Apply”

![rstudio options](/static_images/rstudio-workspace.png)

#### getting to know Rstudio

Notice the default panes:

-   Console (entire left)
-   Environment/History (tabbed in upper right)
-   Files/Plots/Packages/Help (tabbed in lower right)

An important first question: where are we?

If you have opened RStudio for the first time, you’ll be in your Home
directory. This is noted by the ~/ at the top of the console. You can
see too that the Files pane in the lower right shows what is in the Home
directory where you are. You can navigate around within that Files pane
and explore, but note that you won’t change where you are: even as you
click through you’ll still be Home: ~/.

![rstudio layout](/static_images/RStudio_IDE_homedir.png)

You can resize the panes using by dragging in the interstitial space.

**Do This:**

Try using the console as a calculator.

<pre class="r">
<code class="language-r">
```{r eval=FALSE}
10 + 4 # you can add 
10 - 4 # subtract
4 / 2 # divide
2 * 5 # multiply
3 ^ 4 # and exponentiate

# save this to a varialble

x <- 3 ^ 4

#to get the value of a variable, just write it and press enter

x

# you can build up larger expressions too
# remember PEMDAS!

y <- (3 + 4) * 7 + 3
y
```</code></pre>

**Do This:** Use R to calculate what percentage of your life you have
spent in higher education as a student or trainee?

### 3. Create an Rproject

Rprojects make it easy to switch between different tasks. You should
always be using an Rproject when you are using Rstudio. Create one for
this workshop:

**Do This:**  
- Make sure you’ve downloaded and extracted the repo (step 0 above) -
File -&gt; New Project - chose “Existing Directory” - pick that folder.

### 4. R markdown documents

R markdown documents should be your default way of writing R. It allows
you to organize your code into “chunks” and to write plain prose outside
of chunks to document what you are doing.

**Do This:**

#### a. Create a new R markdown document

-   File -&gt; New File -&gt; R Markdown
-   Make the title something sensible
-   got to File -&gt; Save and name it something sensible
-   note: file names should be all lower case and use `_` to separate
    words.

#### b. Insert a code chunk:

-   Code -&gt; Insert Chunk
-   inside your code chunk, write the expression you used above to
    calculate the percentage of your life in higher ed
-   press the green play button to run the chunk
-   edit the code chunk to save this as a variable
-   make it so your code chunk prints the value of the variable when you
    run it

<pre class="r">
<code class="language-r">
```{r}
percent_life_in_higher_ed <- # your code here

```</code></pre>

#### c. Knit your document:

-   At the top of this document is a button called “Knit”
-   Press the button
-   Click “Open in Browser” when your document knits.

#### style guide

Variables should always be all lower case and have underscores between
words. Being consistent will save you tons of time, and this make
variables very readable.

**Do This:**

### variables and types

So far everyting we’ve worked with were numeric values. R has many other
types of data it knows about.

-   `character` values are text. This type is also called `string` in
    other languages.

<pre class="r">
<code class="language-r">
```{r}

"this is a character"
```</code></pre>

There are many functions to work with character values, we might tuch on
it this week.

What happens if you try to add a character to a number?

<pre class="r">
<code class="language-r">
```{r}

"3" + 4
```</code></pre>

### How to read in data

R shines for tabular data. The easiest format to store and read data
into R is `csv` format, which stands for “comma separated values.”
(`tsv`, or “tab separated values” is also great). You can save
individual sheets as a csv in Excel or Google Sheets.

**Do This:** - Open up the `.xlsx` file in the `data` folder. - Save the
first sheet as a `.csv` file into the data folder. (You may need to copy
the sheet into a new excel document)

Now we can read the csv file into R. First, we’ll load the
`tidyverse`library which has the functions we need, then we’ll read the
data in.

**Do This:** Make a new code chunk and read in your `.csv` file.

<pre class="r">
<code class="language-r">
```{r}
library(tidyverse)

fresh_metadata <- read_csv("") # edit this to be the file path of your csv.

```</code></pre>

Then, take a look at the data by clicking on `fresh_metadata` in the
Environment pane (top right)

### `dplyr::filter()`, `dplyr::select()`, `dplyr::arrange()`

Working with tabular data in the `tidyverse` is all about using verbs to
perform actions in an order. To do this you “pipe” your table to a verb.
The pipe operator in R looks like this: `%>%`. you can read this aloud
in your head as “and then”.

#### getting help with functions

In the console type `?select`. The bottom right pane will become a help
screen showing the documentation of that function.

**Do This:** Make a new code chunk to learn how to filter, select, and
arrange. Whenever you see a new code chunk below, make a new one in your
code and write a sentence above it outside of the chunk to say what the
chunk is doing.

-   Go to Help -&gt; Cheatsheets -&gt; Data Transformation with dplyr

<pre class="r">
<code class="language-r">
```{r}

# subset and reorder columns with select

fresh_metadata %>%
  select(study_id)

# try selecting the study id, visit code, and nugent score
```</code></pre>
<pre class="r">
<code class="language-r">
```{r}

# you can add a minus in front of a column to select everything but that column

fresh_metadata %>%
  select(-study_id)

# try selecting everything but the columns with amplicon

```</code></pre>
<pre class="r">
<code class="language-r">
```{r}

# filter rows based on logical expressions

fresh_metadata %>%
  filter(nugent_total_score < 3)

# try filtering rows that have more than 50% lactobacillus iners
```</code></pre>
<pre class="r">
<code class="language-r">
```{r}

# sort rows based on numeric values in a column
# defaults to ascending (low to high). Use `desc()` around the column name to sort high to low.

fresh_metadata %>%
  arrange(amplicon_total_reads)

# try filtering rows that have more than 50% lactobacillus iners,
# and then select only the three columns amplicon_pct_lacto_iners, study_id and visit_code
```</code></pre>

### add new columns with `dplyr::mutate()`

<pre class="r">
<code class="language-r">
```{r}
fresh_metadata %>%
  mutate(total_lacto = amplicon_pct_lacto_non_iners + amplicon_pct_lacto_iners)

# making a column that estimates how many total lacto reads there are
# by multiplying total_lacto by amplicon_total_reads
```</code></pre>

### calculate summaries with `dplyr::summarize()` and `dplyr::group_by()`

Summarising a table means taking all the rows and collapsing it to one
row. You do this with functions that take any number of values and
return just one value, like `mean` or `average`

<pre class="r">
<code class="language-r">
```{r}

fresh_metadata %>%
  summarise(mean_non_iners = mean(amplicon_pct_lacto_non_iners))

# try getting the mean of just the rows with a CT1 microbial community


```</code></pre>

`group_by()` splits your table up by unique values in one or more
columns

<pre class="r">
<code class="language-r">
```{r}

fresh_metadata %>%
  group_by(amplicon_ct_assignment) %>%
  summarise(mean_non_iners = mean(amplicon_pct_lacto_non_iners))

# use the `n()` function inside summarise to see how many 
# records you have with each CT

```</code></pre>
