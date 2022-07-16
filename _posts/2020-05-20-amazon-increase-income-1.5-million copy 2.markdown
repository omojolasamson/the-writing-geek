---
layout: post
title:  ARTICLE - Coping With Stress at Work
excerpt: Everyone who has ever held a job has, at some point, felt the pressure of work-related stress. Any job can have stressful elements, even if you love what you do. 
date:   2020-05-20 15:05:55 +0300
image:  post-5.jpg
---

<!---author: uixgeek
tags:   UX design
---
![post-thumb]({{site.baseurl}}/assets/images/blog/post-1.jpg){:class="img-fluid rounded float-left mr-5 mb-4"}-->


HANDLING MARKDOWN IN PHP Introduction Markdown, initially written in Perl language, was created in 2004 by John Gruber. Markdown was created with the goal of simplifying internet writing. Markdown transforms to HTML effortlessly, relieving you from the inconvenience of writing HTML code. It enables us to write HTML faster and better. The idea around Markdown is that plain text documents must be readable and understandable without the interference of HTML tags, but rather a method to include various attributes for text such as images, paragraphs, line breaks, italics, lists, bold, links, etc. Markdown can be implemented on different platforms such as blogs, Email, Documentation, Note-taking applications e.t.c. The filename extension for Markdown is .md. Best markdown Libraries for PHP PHP has a variety of markdown libraries that offer different features, some of the most common markdown libraries in PHP are, 1 Parsedown 2 cebe/Markdown 3 PHP Markdown 4 Common Mark Each of the Markdowns listed above has unique features they offer. PARSEDOWN One of the most popular markdown libraries for PHP is Parsedown. it was created by Emabuil Rusev. It presently has over 14,000 stars on its GitHub repo. Parsedown has over 97 million installs on packagist. It is the most downloaded PHP markdown parser. Some of the features parse down boasts of are its Extensibility, No Dependencies, One File, Github Flavoured, and it is also the fastest markdown library with One of the easiest implementations. PHP MARKDOWN PHP Markdown currently has over 32 million installs on Packagist, it’s GitHub repo boast of over 3,000 stars. It was created in 2007 by Micheal Fortin. This markdown library package requires PHP 7.4 or later. It is derived from John Gruber's original Markdown.pl. CEBE/MARKDOWN Carsten Brandt created the cebe/markdown Markdown library. It is highly extensible and super fast. Because its method relies on parsing strings rather than the complex regular expressions employed in projects like PHP Markdown, it could be considered more user-friendly. cebe/markdown has more than 12 million downloads on packagist, over 900 stars on GitHub and it is adopted by more than 100 other projects, including Yii 2. COMMON MARK This markdown library was created by Colin O’Dell and several other contributors. It has over 98 million downloads on packagist and over 2,000 stars on GitHub. It is the most thorough markdown library for PHP. CommonMark supports the whole CommonMark spec as well as the entire GitHub-Flavored Markup spec. Additionally, the league/commonmark library has a command-line utility that converts Markdown text with a seamless CLI interface. Choosing the markdown to use for your project will depend on your preference and demands. Comparing the four markdowns highlighted above in terms of speed, Parsedown is the fastest markdown, followed by the PHP markdown, cebe/markdown, and lastly Common Mark. Without a doubt, Common Mark is the most extensible markdown, it offers a good extension system. Installation Using the composer is the preferred approach for installing the PHP Markdown package, to install the markdown of your choice, navigate to the composer and type composer require {package} For example composer require cebe/markdown to install cebe/markdown or composer require erusev/parsedown to install parsedown Handling headers Learning Markdown is quite simple. Creating a heading in markdown does not require you to know a complex syntax, you’ll be surprised how easy it is to create one, all you simply have to do is to add a hashtag (#) in front of the words, for example, (‘ # Creating Markdown’) will display as

Creating markdown

. The number of (#) hashtags will denote the level of header tag to use, for instance, A single hashtag (#) is equivalent to

Double hashtags (##) is equivalent to
And four hashtags (####) are equivalent to

and so on An example using parsedown will look like this, $Parsedown = new Parsedown(); Excho $ Parsedown -> text (‘# My first Markdown’); Which will result in

My first Markdown

Note: Always put a space between the hashtag and the words for compatibility sake. Handling Tables Handling tables in markdown is not a hard task, when working with tables, we make use of hyphens (---) and pipe symbol ( | ). We use the pipe symbol (|) to divide each column and three or more hyphens (---) to create the header for each column. For Example, you can create a file called table.md, in the file input the following syntax. | My Skills | Exp Years | | ----------- | -------------| | PHP | 3 years | |Laravel | 2 years | Ther parse the fie through your markdown with the following syntax (suppose you are using parsedown) Include (Parsedown.php) $table = file_get_content (‘Table.md’); $Parsedown = new Parsedown(); Echo $Parsedown -> text($Table); When parsed to HTML it will look like this

| My Skills | Exp years |
| --------- | --------- |
| PHP       | 3 years   |
| Laravel   | 2 years   |

Handling Links Links in markdown are denoted using the square bracket [ ] and parentheses ( ), the link text will be wrapped in the square bracket, while the link itself will be written in the parentheses. An example of a link in markdown can be, [link to my page](www.mypage.com] which when parsed to HTML will appear as link to my page Handling Images The syntax for Images in markdown is somewhat similar to that of links. The 0nlyl difference is that when defining images an exclamation mark comes before the square bracket. When creating an image, enclose the link in the parentheses and the alt text in the square bracket. Example ![A Pretty image of yourself]( https://image.shutterstock.com/image-photo/young-femalebeautiful-long-hair-260nw-1976765261.jpg) Handling List When working with links in markdown. You can use either asterisk (*) or plus sign (+) or a single hyphen (-), For example, a file with the following content; * First Item * Second Item * Third Item When the file is parsed by parsedown Include (Parsedown.php) $Mylist = file_get_content (‘Mylist.md’); $Parsedown = new Parsedown(); Echo $Parsedown -> text($Mylist); When rendered in HTML, it will appear as follows,

- First Item
- Second Item
- Third Item

Conclusion There are many advantages to using Markdown, and you can accomplish so much more with it. Markdown offers a lot of extended implementations that support formats such as footnotes, indented code blocks and so much more. Should you be interested in learning more about these Markdown implementations, you can check out the official documentation page.
