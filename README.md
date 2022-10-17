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

**Do This:** Use R to calculate what percentage of your life you have
spent in higher education as a student or trainee?

### 3. Create an Rproject

Rprojects make it easy to switch between different tasks. You should
always be using an Rproject when you are using Rstudio. Create one for
this workshop:

**Do This:** - Make sure you’ve downloaded and extracted the repo (step
0 above) - File -&gt; New Project - chose “Existing Directory” - pick
that folder.

### R markdown documents

R markdown documents should be your default way of writing R. It allows
you to organize your code into “chunks” and to write plain prose outside
of chunks to document what you are doing.

Create a new R markdown document **Do This:** - File -&gt; New File
-&gt; R Markdown - Make the title something sensible - got to File -&gt;
Save and name it something sensible - note: file names should be all
lower case and use `_` to separate words.

Insert a code chunk: - Code -&gt; Insert Chunk - inside your code chunk,
write the expression you used above to calculate the percentage of your
life in higher ed - press the green play button to run the chunk - edit
the code chunk to save this as a variable - make it so your code chunk
prints the value of the variable when you run it

<pre class="r">
<code class="language-r">
```{r}
percent_life_in_higher_ed <- # your code here

```</code></pre>

Knit your document: - At the top of this document is a button called
“Knit” - Press the button - Click “Open in Browser” when your document
knits.

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

-   

### How to read in data

R shines for tabular data. The easiest format to store and read data
into R is `csv` format, which stands for “comma separated values.”
(`tsv`, or “tab separated values” is also great). You can save
individual sheets as a csv in Excel or Google Sheets.

### `dplyr::filter()`, `dplyr::select()`, `dplyr::arrange()`

### add new columns with `dplyr::mutate()`

### calculate summaries with `dplyr::summarize()` and `dplyr::group_by()`

### plotting with `ggplot()`
