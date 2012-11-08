--- 

layout: post

title: How to source one ftplugin from another

published: true

description: Something I learned while trying to be awesome

---

I recently read an article about [using Vim for writing
prose](http://alols.github.com/2012/11/07/writing-prose-with-vim/). A lot of
the tips there are really cool, but I don't want or need them for all the types
of files I write in. I do, however, use TeX and Markdown frequently, and who
knows if I'd ever want another file type. So I didn't want to create separate
ftplugin files for each with duplicated content. Plus, duplication is always
bad.

So I figured out how to reference one `ftplugin` file from another. I created
`prose.vim` with all the stuff I wanted to use in my writing files (e.g.,
`.tex` and `.markdown`). I put that one in the `ftplugin` directory.

Then I created `markdown.vim` and `tex.vim` and added the following line to
both of them. This made all the difference

	runtime! ftplugin/prose.vim

With that, I load my prose.vim file any time I use markdown or tex files. And
any time I want to change the way those act, I can just make changes in one
place: `prose.vim`.

Hope that helps somebody.
