## Intro to R and R studio

Today we’re going to get started with R and Rstudio. By the end of
today’s session, you should know how to :

-   Change options in Rstudio
-   Create an Rmarkdown document
-   Use different types of data in R
-   Read in tabular data like a csv file
-   Make quick summaries of dataframes
-   Create new columns in dataframes

### 0. Download today’s materials

\*\* Do This: \*\*  
- Go to <https://github.com/elsherbini/kwonlab_R_workshop_20221017> -
Click on the green “Code” button and “Download Zip” - Move the zip file
somewhere sensible and unzip it

### 1. What is R and Rstudio?

R is a programming language, which means you can write programs as text
that adheres to a syntax and R will interpret your program into
instructions for the computer. R was released in 1995, but it was based
on an older language from 1976. Because it is so old, there is sometimes
ugly syntax or several ways to do the same thing, which is confusing.

Rstudio is the name for this code editor, and also the team who makes
the `tidyverse` set of packages. These packages try to make using R more
powerful and less confusing for working with data.

#### changing options

\*\* Do This: \*\*  
- Open up RStudio - Got to Tools -&gt; Global Options . - Under
Workspace, uncheck “Restore .RData into workspace on startup” - Change
“Save workspace to .RData on exit” to “Never” - Switch to the Appearance
pane on the left, and look at different themes. - Try Dracula, Cobalt,
and Tomorrow Night 80s. Pick any theme you want and git “Apply”

![rstudio options](/static_images/rstudio-workspace.png)

#### getting to know Rstudio

### 2. Create an Rproject

Rprojects make it easy to switch between different tasks. You should
always be using an Rproject when you are using Rstudio. Create one for
this workshop:

\*\* Do This: \*\* - Make sure you’ve downloaded and extracted the repo
(step 0 above) - File -&gt; New Project - chose “Existing Directory” -
pick that folder.

### R markdown documents

Create a new R markdown document \*\* Do This: \*\* - File -&gt; New
File -&gt; R Markdown - Make the title something sensible - got to File
-&gt; Save and name it something sensible - note: file names should be
all lower case and use `_` to separate words.

Insert a code chunk: Code -&gt; Insert Chunk

#### style guide

### variables and types

### How to read in data

#### `here()`

### `dplyr::filter()`, `dplyr::select()`, `dplyr::arrange()`

### add new columns with `dplyr::mutate()`

### calculate summaries with `dplyr::summarize()` and `dplyr::group_by()`

### plotting with `ggplot()`
