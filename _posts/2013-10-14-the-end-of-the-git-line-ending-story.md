---
layout: blogpost
categories: Opinion
---

# The end of the Git Line Ending Story?

<img class="alignnone size-full wp-image-385" alt="boromir_meme_one_does_not_simply_let_git_handle_line_endings" src="https://steen.hulthin.dk/blog/wp-content/uploads/2013/10/boromir_meme_one_does_not_simply_let_git_handle_line_endings.jpg" width="480" height="283" />

Git wants to help you handle line endings in text files (which are different on different platforms) so your code can be easily shared across platforms. To be able to help you with this git needs to know what you consider to be text files (and which files you consider to be binary). You do that by adding a <code>.gitattributes</code> file in the repository (alongside the <code>.git</code> folder). The <code>.gitattributes</code> file should at least contain the line <code>* text=auto</code> (the lazy way) which let's git determine which file are text. However adding a line like:
<code>*.txt text</code>
or
<code>*.jpg binary</code>
for each text file type is the most declarative/precise way to tell git which files are text and which files are binary.

An alternative starting point for a <code>.gitattributes</code> file is the one <a title="github for windows" href="http://windows.github.com/">github for windows application</a> creates for you. It looks like this:

{% highlight txt %}

# Auto detect text files and perform LF normalization
* text=auto
# Custom for Visual Studio
*.cs diff=csharp
*.sln merge=union
*.csproj merge=union
*.vbproj merge=union
*.fsproj merge=union
*.dbproj merge=union
# Standard to msysgit
*.doc diff=astextplain
*.DOC diff=astextplain
*.docx diff=astextplain
*.DOCX diff=astextplain
*.dot diff=astextplain
*.DOT diff=astextplain
*.pdf diff=astextplain
*.PDF diff=astextplain
*.rtf diff=astextplain
*.RTF diff=astextplain

{% endhighlight %}

If you read only one more thing about this I think you should make it <a title="stackoverflow answer on best strategy for line ending handling in git" href="http://stackoverflow.com/a/10855862/587279">this stackoverflow answer</a>.

Other references:
.gitattribute documention
<a href="https://help.github.com/articles/dealing-with-line-endings#per-repository-settings">https://help.github.com/articles/dealing-with-line-endings#per-repository-settings</a>
<a href="https://www.kernel.org/pub/software/scm/git/docs/gitattributes.html#_end_of_line_conversion">https://www.kernel.org/pub/software/scm/git/docs/gitattributes.html#_end_of_line_conversion</a>
git line ending history (and why it matters)
<a href="http://adaptivepatchwork.com/2012/03/01/mind-the-end-of-your-line/">http://adaptivepatchwork.com/2012/03/01/mind-the-end-of-your-line/</a>