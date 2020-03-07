# Introduction {#intro}
跑出單一章節的方法

```r
bookdown::preview_chapter("01-intro.rmd", "bookdown::gitbook")
```
注意換行要在結束句輸入「兩」個空格，才換行。不然就要按兩次enter鍵。  
一個空格只是單純的空格，「兩」個空格才會有新的意義，如換行或內縮（在列點時用）。  
圖形帶有中文字時，在一開始的chunk設定：

```r
knitr::opts_chunk$set(fig.showtext=TRUE)
library(showtext)
showtext_auto()
```
若想使用自己電腦字體，可先執行如下指令：

```r
font_add(family="yuan",regular="/Users/martin/Library/Fonts/cwTeXQYuan-Medium.ttf")
```
其中regular後面是你電腦的字型檔，而family用來設定此字型檔在你程式中的名稱。  
上例引入cwTeXQYuan-Medium.ttf字型檔，並稱它為“yuan”。  
  

加速(紀錄曾跑過的)，如果沒有動到code就不會重跑  
{r 簡介4,eval=FALSE, cache = TRUE, include=TRUE}  

YAML可以放在第1個的.RMD檔內，也可放在各自的 _output.yml裡  
內嵌其他的網頁!
knitr::include_app()  


可作互動式網頁!  
HTML widgets  


You can label chapter and section titles using `{#label}` after them, e.g., we can reference Chapter \@ref(intro). If you do not manually label them, there will be automatic labels anyway, e.g., Chapter \@ref(methods).

Figures and tables with captions will be placed in `figure` and `table` environments, respectively.


```r
par(mar = c(4, 4, .1, .1))
plot(pressure, type = 'b', pch = 19)
```

<div class="figure" style="text-align: center">
<img src="01-intro_files/figure-html/nice-fig-1.png" alt="Here is a nice figure!" width="80%" />
<p class="caption">(\#fig:nice-fig)Here is a nice figure!</p>
</div>

Reference a figure by its code chunk label with the `fig:` prefix, e.g., see Figure \@ref(fig:nice-fig). Similarly, you can reference tables generated from `knitr::kable()`, e.g., see Table \@ref(tab:nice-tab).


```r
knitr::kable(
  head(iris, 20), caption = 'Here is a nice table!',
  booktabs = TRUE
)
```



Table: (\#tab:nice-tab)Here is a nice table!

 Sepal.Length   Sepal.Width   Petal.Length   Petal.Width  Species 
-------------  ------------  -------------  ------------  --------
          5.1           3.5            1.4           0.2  setosa  
          4.9           3.0            1.4           0.2  setosa  
          4.7           3.2            1.3           0.2  setosa  
          4.6           3.1            1.5           0.2  setosa  
          5.0           3.6            1.4           0.2  setosa  
          5.4           3.9            1.7           0.4  setosa  
          4.6           3.4            1.4           0.3  setosa  
          5.0           3.4            1.5           0.2  setosa  
          4.4           2.9            1.4           0.2  setosa  
          4.9           3.1            1.5           0.1  setosa  
          5.4           3.7            1.5           0.2  setosa  
          4.8           3.4            1.6           0.2  setosa  
          4.8           3.0            1.4           0.1  setosa  
          4.3           3.0            1.1           0.1  setosa  
          5.8           4.0            1.2           0.2  setosa  
          5.7           4.4            1.5           0.4  setosa  
          5.4           3.9            1.3           0.4  setosa  
          5.1           3.5            1.4           0.3  setosa  
          5.7           3.8            1.7           0.3  setosa  
          5.1           3.8            1.5           0.3  setosa  

You can write citations, too. For example, we are using the **bookdown** package [@R-bookdown] in this sample book, which was built on top of R Markdown and **knitr** [@xie2015].
