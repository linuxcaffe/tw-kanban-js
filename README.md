## Taskwarrior-Kanban 
(forked from Simple-Kanban)

Simple Kanban is/was a single-html-file kanban board, written by Stephan Schmidt, and formerly hosted at http://scm.zoomquiet.io/data/20110709023400/index.html#Download and (now empty repository) https://github.com/StephanSchmidt/SimpleKanban. 
There was only ever one release, and now the github repo has been cleared out, empty, and all the links are 404.

Luckily, I had a copy of one of the magic html files, and it was released inder the MIT license, and so I'm taking the liberty of preserving it, and hoping to develop from it into a taskwarrior-specific thing.

To understand why this might be interesting at all, you MUST download the kanban.html file above, and open it in a browser. Then this will ALL make more sense. It's brilliant!

The end-goal is to develop a simple and effective kanban board for taskwarrior.org . 
Using a UDA "state:" that defines what state (if any) a task is in, tasks could then be visually Drag and Dropped frome one state to another (from one "swimlane" or "story" to another) and using javascript interacting with task.

![](https://raw.githubusercontent.com/linuxcaffe/Taskwarrior-Kanban/dev/kanban_screenshot1_small.png)

----
### Original Docs


<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>Simple-Kanban | The one file kanban board application</title>
<link rel="stylesheet" type="text/css" href="index.css" media="all">
</head>
<body>
<!-- <div class="container_12">
<div class="grid_12 alpha omegs">
<img src="images/ScreenPhoto.jpg" alt="Simple Kanban screen photo"/>
</div>
</div>
--><div class="container_12">
<img class="logo" src="logo.png" alt="Simple Kanban Logo" border="0">
<h1>A Kanban Board Application in Simply One Html File</h1>
</div>
<div class="container_12">
<div class="grid_9 alpha">
<h2>What is Simple-Kanban?</h2>
<p>
Simple-Kanban is a Kanban board application and can be used in
<a href="http://en.wikipedia.org/wiki/Lean_software_development">lean software development</a>.
While introducing lean practices, I've needed a small, simple
<a href="http://www.infoq.com/articles/agile-kanban-boards">Kanban Board</a> application.
Decided I'd write one.
</p>
<p><a href="http://www.simple-kanban.com/download/Simple_Kanban_App_1.0RC1.html"><img alt="Simple Kanban Screenshot 1" src="screenshot1_small.png" border="0"></a></p>
<p>You can download a first 1.0 RC version <a href="#Download">here</a> or see it in action
<a href="http://www.simple-kanban.com/download/Simple_Kanban_App_1.0RC1.html">here</a>. <b>Simple-Kanban</b> is Open Source software,
free for personal and commercial use and licensed under a MIT license.</p>
<p><b>Suprised?</b> The application is just one HTML file, no installation needed, no Java, Ruby or PHP.
One HTML file, no other dependencies.</p>
<h2>Why should I use Simple-Kanban?</h2>
<p>
If you're working in stories, use Kanban, Scrum, or another agile approach, <b>you should use a Story/Kanban board</b>.
Simple-Kanban is an application to manage such a Kanban board. A Kanban board <b>informs a company about the stories which are in
development</b> and in which state they are. Everyone knows what's happening, because such a board is an ideal
<a href="http://alistair.cockburn.us/Information+radiator">information radiator</a>. This leads to more
transparency and less status meetings or questions to your developers about project status. With a Kanban
board you can see bottlenecks, adress them and optimize flow through your organisation.
</p>
<b>Best to use Simple-Kanban on a
huge screen</b>, if you do so, please send me a picture if possible.
<p></p>
<h2>How to use Simple-Kanban?</h2>
<p>You can drag stories around and drop them in every column. If you want to edit the stories, add stories or
remove stories, click on the "Data" link in the top right corner. You will find a list
of stories. The example contains those:</p>
<pre>T_Q,S18,Checkout optimize
DE,S2,Build old shop
DE,S4,Rebuild with SOAP
DE_Q,S10,Rebuild with REST
P,S17,Do something with OpenID
D,S3,Make application faster
D_Q,S7,Credit Card Payment
DE,S13,Build something astonishing
P_Q,S17,Fix YSlow
R,S39,Google Page Speed fix
</pre>
<p>There are three columns for stories. The first column contains the state the story is in, the second contains
an identifier for your story and the last column the name of the story. You can edit the columns, change
states, change names, remove and add stories. You can also export form Excel to csv, then cut&amp; into the
application source.</p>
<p>
After your satisfied with your changes and want to go back to the Simple-Kanban board view, click
on the top right corner on "Board". Simple-Kanban will then change back to the board view.
</p>
<h3>How do I save the stories?</h3>
<p>
Go to the data view and copy all stories. Then simply edit the source of the HTML file
with an editor of your choice, preferably one which knows HTML. There you can paste the copied
stories over the old ones and save the HTML file.
</p>
<h3>How do I change the possible states?</h3>
<p>When looking into the source file, the available states are described next in the block after the
stories:</p>
<pre>D,Design
DE,Development
T,Test
R,Release
</pre>
<p>
You can edit them in the source file just as you like. If you save the HTML file, the states are save too.
The states need to be available for the stories and match the states of the stories. You can add, remove or
change
states. Every state has a "sub-state" as a ready queue. For example the ready queue state for Design "D"
is "D_Q", for Test"T" it is "T_Q". You do not need to describe the ready
states, they are automatically created and a ready queue is shown in front of every state. For example
"Test Ready" is shown left to "Test".
</p>
<h2>Customize the colors</h2>
<p>The colors of each state are defined in a CSS block.</p>
<pre> #D .box { background-color: #FFC300; color: #000000;}
#D_Q .box { background-color: #F0F0F0; color: #606060;}
</pre>
<p>Feel free to change them to your taste. "#D .box" is for the boxes in the "D" column, "D_Q .box" is for the
for the corresponding ready queue.</p>
<h2>Future</h2>
<p>
I'm thinking about a <a href="http://couchdb.apache.org/">CouchDB</a> storage implementation for storing
data and application logic. Or storing data in the file like <a href="http://www.tiddlywiki.com/">TiddlyWiki</a>
does. Future lean features? Add WIP limits, add "From here" signs to display cycle time until live. Have fun
with
this One-File-HTML-application. <b>Tip:</b> you can easily mail it around, to developers,
product manager, your boss or top managment. No install needed.</p>
<a name="Download"><h2>Download</h2></a>
<p>There are several packages for download. <em>To download
Simple-Kanban, save the HTML page or save the link with "Save link as..."</em>
<b>Simple-Kanban</b> is Open Source software, free for personal and commercial use and licensed under a MIT
license.
</p>
<p class="downloadarea">
<a href="http://www.simple-kanban.com/download/Simple_Kanban_App_1.0RC1.html">Simple Kanban 1.0RC1 example file</a><br>
<a href="http://www.simple-kanban.com/download/Simple_Kanban_App_1.0RC1_Empty.html">Simple Kanban 1.0RC1 empty file</a> to start<br>
<a href="http://www.simple-kanban.com/download/Simple_Kanban_App_1.0RC1.zip">Simple Kanban 1.0RC1 ZIP file</a> with all files<br>
</p>
<a name="Source"></a><h2>Source Code</h2>
The source code is hosted on <a href="http://github.com/StephanSchmidt/SimpleKanban/tree/master">Gitbub</a>
<pre>http://github.com/StephanSchmidt/SimpleKanban/tree/master
</pre>
</div>
<div class="grid_3 omega">
<div id="downloadbox">
<b>Download Simple-Kanban</b>
<p>
You can download a very first 1.0 RC version <a href="#Download">here</a>.
<b>Simple-Kanban</b> is Open Source, free for personal and commercial use and licensed under a MIT license.
</p>
</div>
<div id="sourcebox">
<b>Source code</b>
<p>The source code can be found on <a href="#source">Github</a></p>
</div>
<p><b>If you like Simple-Kanban,</b> and would like to learn more
about lean, Kanban and software development, follow me on by blog at <a href="http://www.codemonkeyism.com/">codemonkeyism.com</a>
or twitter about Simple-Kanban: </p>
</div>
</div>
</body>
</html>
