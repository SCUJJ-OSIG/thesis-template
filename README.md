# 四川大学锦江学院毕业论文Latex模板

> 模板改自电子科技大学中山学院，中山学院提供的教程verygood，在学习使用的时候可以完全按照这个教程

## 干货

1. 使用Latex模板撰写论文，可以让你只关注内容，而不被格式困扰。可以先看一下本模板的[最终效果](https://v1.overleaf.com/latex/templates/zsc-sc-thesis/bvhhjhgvpjbx.pdf)。
2. 不过，Latex的使用稍微需要一点点学习成本。
3. Latex模板撰写的论文最终输出成PDF文档，当然不可能和Word一模一样。
4. 简单看一下[B站视频教程](https://www.bilibili.com/video/av328559652)，直接使用[Overleaf模板](https://cn.overleaf.com/latex/templates/zsc-sc-thesis/bvhhjhgvpjbx)，Open as Template，肝就是了。
5. 如果觉得表格编辑有点麻烦，可以搜索并使用一些在线latex表格工具来生成表格。
6. 如果图片导致文中有大段空白，可以通过调整文字和图片的位置，以及设置正确的浮动方式，来抑制文中的大段空白。
7. 切记，参考文献，一定要在文中引用，才能出现在最后的参考文献章节。
8. 切记，图片和表格一定要在文中引用，千万不能写，如下图，如下表。

## 问题反馈
email: tzd15@qq.com

---

<font size=6>**以下太长不看版**</font>

## why 
毕业季，大家为了论文而忙碌。在答辩的前几天，如果你的论文使用了Word模板，通常会因为各种[格式问题](https://gitee.com/yeyunxiaopan/zsc-cs-latex-thesis/issues/I3P275)而抓狂。为了让大家从中解脱出来，我们设计了四川大学锦江学院毕业论文Latex模板，推荐大家使用Latex来完成毕业论文。

## what

Latex是免费的文档排版编译系统，Latex模板分离了论文的内容和格式。对于使用者来说，只要关注论文本身的内容，而不用关注论文的格式，比如字号，字体，交叉引用，目录等，这些排版的事情都交给Latex模板即可，最终你可以得到一本格式正确的PDF论文。

## how 

建议直接使用在线的[Overleaf](https://cn.overleaf.com)在线环境。

---
## Overleaf 
1. [Overleaf](https://cn.overleaf.com)是在线的Latex编辑编译系统
2. 免去小白用户安装配置本地编译环境的苦恼
3. 非常利于团队多人合作来撰写论文
4. 包含大量精美的模板，不仅限于论文写作，还可以完成很多其它的文档，比如个人简历制作。 
5. 首次使用，请先利用邮箱注册账号，注册成功，应该会收到激活邮件，根据提示激活一下账号，否则可能无法正常使用。

## Overleaf使用四川大学锦江学院毕设论文模板

1. 直接打开（后续加网址）
2. Open as Template, 生成一个新的项目
3. 编辑论文内容, 编译生成pdf格式的论文

---

## 模板的结构

```
thesis 
|   main.tex (tex源码，其input了tex目录中的文件)
|   make.bat (Windows编译脚本)
|   make.sh  (Linux编译脚本)
|   
+---bib 
|       gbt7714-numerical.bst (参考文献样式)
|       ref.bib (BIBTEX参考文献数据库文件)
|       
+---img (论文中需要插入的图片放到此目录)
|       fig1.png (图片)
|       ...
|       
+---logo (学校的logo)
|       logo.png
|       uestc.pdf
|       
+---sign (原创声明页手写签名图片)
|       advisor.png  (导师签名)
|       author.png   (作者签名)
|  
+---style
|       zsccode.sty    (源代码样式)
|       zscexample.sty (例子样式)
|       zscthesis.cfg  (配置文件)
|       zscthesis.cls  (封装导言区，需要额外的宏包，在此添加)
|       
+---tex (如果增加新的章节，先在此目录下增加tex文件，再修改main.tex)
|       frontinfo.tex       (封面)
|       declaration.tex     (独创性声明，如无需要，不用修改)
|       abstract-ch.tex     (中文摘要)
|       abstract-en.tex     (英文摘要)
|       content.tex         (目录，图目录，表目录，如无需要，不用修改)
|       chap-1.tex          (第1章)
|       chap-2.tex          (第2章)
|       chap-3.tex          (第3章)
|       chap-4.tex          (第4章)
|       chap-5.tex          (第5章)
|       chap-6.tex          (第6章)
|       reference.tex       (参考文献，如无需要，不用修改)
|       appendix.tex        (附录，如果没有内容，在main.tex中注释掉)
|       acknowledgement.tex (致谢)
|       
\---tmp (编译结果)
    |   main.pdf (最终的pdf文档)

```


## 模板的使用

### 基本语法 
1. 普通文本
2. 注释 `%`
3. 环境 `\begin{环境名}[可选参数]{必须参数} ... \end{环境名}`
   - 公式 `\begin{equation} ... \end{equation}`
   - 图片 `\begin{figure}[H] ... \end{figure}`
4. 命令 `\命令名[可选参数]{必须参数}`
   - 居中 `\centering`
   - 加载 `\input{tex/frontinfo.tex}`
5. 换行需要两次回车，也就是tex源码中一个空行，pdf文档才能换行

### 封面 
1. tex/frontinfo.tex
2. 使用相应的命令来设置相关信息
   - 论文题目`\mytitle{}`
   - 完成时间`\completedate{}`
3. 把个人信息填入相应的`{}`中
4. 团队论文
   - 学号用`\\`分隔
   - 学生用`~`分隔
5. 多个指导老师
   - 用`\\`分隔

### 原创声明页
1. tex/declaration.tex
2. 此页内容自动生成，不用手动修改
3. 替换导师签名图片文件 sign/advisor.png 
4. 替换作者签名图片文件 sign/author.png

### 摘要  
1. 中文 tex/abstract-ch.tex
2. 英文 tex/abstract-en.tex
3. 增加摘要内容`\abstract{}`
4. 填入关键词`\keywords{}`


### 目录 
1. tex/content.tex
2. 包含了目录，图目录，表目录
3. 目录是自动生成的，不用手动修改


### 章节
1. tex/chap-1.tex
2. 章，使用命令`\chapter`
   - 章的序号自动添加
   - 章会自动进入目录，页眉等处
   - `\chapter{绪论}`
3. 节，使用命令`\section`，`\subsection`，`\subsubsection`
   - 节的序号自动添加
   - 除了`\subsubsection`，其它节进入目录
   - `\section{课题背景}`


### 增加新的章
1. 在tex目录下新建一个chap-n.tex文件
   - 在其中按照已有章节设置格式和内容
   - 最简单的是复制已有章节，修改其标题和内容即可
2. 在main.tex中，按照章的顺序，在合适位置，使用命令`\input`
   - `\input{tex/chap-n.tex}`
3. 增加之后，目录和文档内容都会发生相应变化

### 有序列表
1. tex/chap-1.tex
2. 使用环境 `enumerate`
   ```
   \begin{enumerate}
      \item 希腊
      \item 罗马 
   \end{enumerate}
   ```
3. 不用手动添加序号
4. 可以进行列表的嵌套

### 无序列表 
1. tex/chap-1.tex
2. 使用环境 `itemize`
   ```
   \begin{itemize}
      \item 古希腊
      \item 古罗马 
   \end{itemize}
   ```

### 参考文献
1. tex/reference.tex 不用修改此文件
   - 包含参考文献的样式
   - 包含BIBTEX数据库文件
2. bib/ref.bib 被引的文献按照格式加到此文件
   - 一般的中文文献都可以借助百度学术找到相应的bib，英文文献则可以借助google学术找到相应的bib 
   - 如果实在找不到，可以手动填写，其中的关键字和规则，可以参考[gbt7714-bibtex](https://github.com/CTeX-org/gbt7714-bibtex-style)
   - 例子中的`chen2005laser`是参考文献的标签 (注意：标签不能重复)，标签主要用于引用，多个作者用and分隔
   ```
   @book{chen2005laser,
      title={现代激光焊接技术},
      author={陈彦宾 and 刘艳红},
      volume={42},
      year={2005},
      publisher={科学出版社}
   }
   ```
3. tex/chap-1.tex 
4. 引用处使用命令`\cite`，引用文献的标签
   - `这是一句引用参考文献的例子\cite{chen2005laser}`

#### 百度学术的用法 
1. 搜索某个关键字，比如 激光
2. 在某个结果中找到 引用
   <div align=center> 
      <img src="ug/img/bib-004.png" width="50%" >
   </div>  
3. 进入引用界面
   <div align=center> 
      <img src="ug/img/bib-005.png" width="50%" >
   </div>  
4. 进入BibTeX
   <div align=center> 
      <img src="ug/img/bib-006.png" width="50%" >
   </div>  
5. 复制内容到bib/ref.bib即可

#### google学术的用法
1. 搜索某个关键字，比如 laser
2. 在某个结果中找到 ”
   <div align=center> 
      <img src="ug/img/bib-001.png" width="50%" >
   </div>  
3. 进入引用界面
   <div align=center> 
      <img src="ug/img/bib-002.png" width="50%" >
   </div>  
4. 进入BibTeX
   <div align=center> 
      <img src="ug/img/bib-003.png" width="50%" >
   </div>  
5. 复制内容到bib/ref.bib即可



### 数学公式
1. tex/chap-2.tex
2. 行内公式
   - 使用`$ $`
   - `$e=mc^2$`
3. 行间公式
   - 使用环境`equation`
   - 如果要引用，使用命令`\label`添加标签 (注意：标签不能重复)
   ``` 
   \begin{equation}\label{eq:newton}
      \vec{F}=m\vec{a} 
   \end{equation}
   ```
4. 公式引用，使用命令`\eqref`，引用标签
   - `如公式\eqref{eq:newton}所示`


### 图片
1. tex/chap-3.tex
2. xelatex 支持的图片格式包括
   - 矢量图: .pdf .eps
   - 位图: .jpg .png .bmp
3. 图片尽量使用矢量图
   - 使用矢量图，pdf格式，可以用visio画流程图导出成pdf格式
   - 矢量图易于调整分辨率，减少空白
   - 如果实在文中空白过大，可以把大图放到附录
4. 图片文件放到img目录 
5. 插入图片
   - 使用环境`figure`
   - 使用命令`\centering`，设置位置
   - 使用命令`\includegraphics`，引入图片
   - 使用命令`\caption`，设置标题，不需要设置序号，标题会自动进入图目录
   - 使用命令`\label`，添加标签，(注意：标签不能重复)
   ```
   \begin{figure}[H]  % [H] 浮动优先级，当前位置 
      \centering % 居中
      % width=.5\textwidth 文档宽度的0.5
      % fig1图片放在img目录下，在此处引用无需img/前缀和图片格式后缀(png, jpg等)
      \includegraphics[width=.5\textwidth]{fig1} 
      \caption{图的标题}
      \label{fig:single}  % label紧接caption之后，用于引用
   \end{figure}
   ```
6. 引用图片，使用命令`\ref`，引用标签
   - `如图\ref{fig:single}所示` 


### 表格
1. tex/chap-5.tex
2. 表格 
   - 使用环境`table`
   - 使用命令`\caption`，设置标题，不需要设置序号，标题会自动进入表目录
   - 使用命令`\label`，添加标签， (注意：标签不能重复)
   - 使用环境`tabular`，设置每格内容居中`{|c|c|c|c|}`
   - 使用命令`\hline`，表示表格的横线 
   - 用`&`来分隔不同的列
   - 用`\\`来分隔不同的行
   ```
   \begin{table}[H] % H 浮动优先级
      \zihao{5} % 字号5
      \centering  % 居中
      \caption{一个表格}  % 表格标题
      \label{tab:tab1}  % 用于引用的label
      % 字母的个数对应列数，|代表分割线
      % l代表左对齐，c代表居中，r代表右对齐
      \begin{tabular}{|c|c|c|c|}   
         \hline  % 表格的横线 
         1 & 2 & 3 & 4 \\  % 表格中的内容，用&分开，\\表示下一行
         \hline 
         0.1 & 0.2 & 0.3 & 0.4 \\
         \hline
      \end{tabular}
   \end{table}
   ```
3. 表格引用，使用命令`\ref`，引用标签
   - `如表\ref{tab:tab1}所示`
4. 如果觉得表格编辑有点麻烦，可以使用在线工具。



### 源码 
1. tex/chap-4.tex
2. 使用自定义的环境`clan`，`matlab`等
   ```
   \begin{clan}
      #include <stdio.h>  
      int main()                  //main 入口函数  
      {  
         printf("Hello,World!"); //printf 函数打印  
         return 1;               //函数返回值  
      }   
   \end{clan}
   ```
3. 源码的格式在 style/zsccode.sty, 如果需要其它风格的源码，可以自行定制
   - 定制方法参考文档 listings.pdf
   - 在命令行运行 `texdoc listings` 即可打开

### 附录 
1. tex/appendix.tex 
2. 附录有自己的章节chapter和section，可以认为是独立的文档
3. 增加相关的附录内容
4. 如果没有附录内容，就在main.tex中注释掉


### 致谢 
1. tex/acknowledgement.tex
2. 修改致谢的内容


### 定制导言区 
1. 适合喜欢折腾的用户
2. style/zscthesis.cls 
3. 如果需要一些高级功能
   - 可以在导言区增加相应的宏包
   - 自定义命令
   - 自定义环境等

## 文件格式
1. 源代码文件 .tex 
2. .sty 宏包文件。宏包的名称与文件名一致。
3. .cls 文档类文件。文档类名称与文件名一致。
4. .bib BIBTEX 参考文献数据库文件。
5. .bst BIBTEX 用到的参考文献格式模板
6. .log 排版引擎生成的日志文件，供排查错误使用。
7. .aux LATEX 生成的主辅助文件，记录交叉引用、目录、参考文献的引用等。
8. .toc LATEX 生成的目录记录文件。
9. .lof LATEX 生成的图片目录记录文件。
10. .lot LATEX 生成的表格目录记录文件。
11. .bbl BIBTEX 生成的参考文献记录文件。
12. .blg BIBTEX 生成的日志文件。
13. .idx LATEX 生成的供 makeindex 处理的索引记录文件。
14. .ind makeindex 处理 .idx 生成的用于排版的格式化索引文件。
15. .ilg makeindex 生成的日志文件。
16. .out hyperref 宏包生成的 PDF 书签记录文件。

## 基本命令
1. 编译 xelatex bibtex
   比如我们的编译脚本中的用法
   比如TeXstudio配置选项中的用法
2. 查看帮助文档 texdoc
   比如查看宏包ctex的帮助文档 `texdoc ctex`

---


## 注意事项
1. 请先浏览[2017级模板使用情况](https://gitee.com/yeyunxiaopan/zsc-cs-latex-thesis/issues/I3P25X)，对可能遇到的问题做到心中有数
2. Latex不能直接输出成Word，并且无法做到所见即所得，请与你的指导老师沟通之后，再慎重考虑是否使用本模板
3. Latex不适合无脑用户，初学者会遇到很多[问题](https://gitee.com/yeyunxiaopan/zsc-cs-latex-thesis/issues/I3OZ5L)，如果你没有基本的代码修养，请放弃使用本模板
4. Latex模板的最终结果无法做到和Word模板一模一样，比如封面的Logo就不同，如果你有强迫症，请放弃使用本模板
5. 请论文指导老师不要逼迫使用Latex模板的学生去修改最终的格式做到与Word模板完全一样，这是不可能的。因为Latex模板分离了内容和格式，学生仅需关注论文的内容，无需关注论文的格式。学生基本上没有能力也没有必要自己去修改格式
6. 本模板在Windows10和Ubuntu1604下测试通过
7. 本模板在Overleaf下测试通过
8. 本模板使用编译系统TeXLive2020, 可能会与TeXLive2021等其它版本的编译系统产生冲突
9. 本模板使用编译器为XeLaTex
10. tex文档编码必须使用UTF-8
11. 本模板可能还有很多意想不到的格式以及兼容性问题
12. [常见问题](https://gitee.com/yeyunxiaopan/zsc-cs-latex-thesis/issues/I3OZ5L)


## 配套的资源
1. [在线模板和使用环境(Overleaf)](https://cn.overleaf.com/latex/templates/zsc-sc-thesis/bvhhjhgvpjbx)，使用Overleaf就不需要搭建本地环境了，也便于师生合作。

2. [源码和文本教程(gitee)](https://gitee.com/yeyunxiaopan/zsc-cs-latex-thesis)，就是这里啦。

3. [配套的视频教程(B站)](https://www.bilibili.com/video/av328559652)，和gitee的文字教程是一一对应的。

4. [文本+视频教程(泛雅)](https://mooc1-1.chaoxing.com/course/212385065.html)，就是以上二者的综合体。

   



## 参考文档
1. 刘海洋.LATEX入门[M].北京:电子工业出版社，2013. (中山学院图书馆索书号: TS803.23/L628)
2. 刘小平.论文排版实用教程:Word与LaTeX[M].北京:清华大学出版社，2015. (中山学院图书馆索书号: TS803.23/L694)
3. 胡伟.LaTeX2e文类和宏包学习手册[M].清华大学出版社，2017. (中山学院图书馆索书号: TS803.23/H513)
4. [中国科学院大学学位论文模板ucasthesis](https://github.com/mohuangrui/ucasthesis)
5. CTEX开发小组.[一份不太简短的LaTeX2e介绍](http://mirrors.cqu.edu.cn/CTAN/info/lshort/chinese/lshort-zh-cn.pdf)
6. Liam Huang.[一份其实很短的 LaTeX 入门文档](https://liam.page/2014/09/08/latex-introduction/)


## 贡献者
tzd，cjj，jzx

