# Danish Developer Conference 2013

The Danish Developer Conference is a one day conference with a very strong Microsoft technology focus. This year it had a double location setup. First location was Horsens (2nd April) and the second location was Copenhagen (4th April). I attended the conference in Copenhagen. The conference site was one of the major cinemas in Copenhagen - Cinemaxx. It worked out fairly well with the cinema rooms as presentation room. The fact that there are no windows in cinema rooms is a drawback though - a whole day of talks in vampire light conditions makes my canines grow. 

<h1>Talks</h1>
The conference programme was full of Danish speakers (14 of the 16 speakers were Danish speaking). Not only that but all the talks I attended were in Danish (with exception of Jon Galloway's keynote). That was a bit weird for me (and actually surprising), but it worked out fine and it probably have the benefit of attracting a few people that would not go if the content had mainly been in English. There were 4 tracks (Windows 8, Windows Phone, Tools & Frameworks and Webudvikling) and a starting and an ending keynote.

<h2>Opening Keynote by Jon Galloway</h2>
The first keynote speaker was <a href="https://twitter.com/jongalloway">Jon Galloway</a>. Jon talked about how we as developer can keep up to date with all the new technology. Jon talked knowledge of different technologies as an investment "game". I can invest time only so much time (as of now time is a limited resource - timetravel FAIL!). Since software technology moves so fast investing all the time in one technology is most likely a fairly bad idea (that technology may be dead in 3 years and I have assignment in many different technologies - you probably have too). 

Jon suggested using some tools that suits you for managing information sources on technology (for instance twitter, G+, blogs and/or podcasts - the latter optionally in 2.5 times normal speed! - I'm going to try that out!). 

From all these sources you can then invest more in the ones that keeps popping up in your information sources or the ones that seems most useful to you. From more information sources you can most likely also extract how to learn a bit more about that specific technology fastest. Through limited time investment you can gradually building up your knowledge of the technologies that are most relevant to you and create a mental model of how that technology works. Most of those technologies will stay on that knowledge level - it looks interesting, you have a good idea about how they work and you will never have time to try it out. (you know I'm right - face it! - well actually Jon is right.)

But a few of the technologies you will actually sit down and use - either because you need something like it in your current project or because you have too few 1½ year old boys to keep you occupied. You can now go on and try out the technology with a good idea of how it works, because you have already made small investments in the technology for some time. Hopefully also with knowledge about how to get started as fast as possible. 

And now I get to another of Jon's points: after actually using the technology, you find out that it does NOT work for you the way you need. #FAIL! Bummer. 

That's not such a bad thing. You now have a even better idea about how that technology works AND you might get to try to solve your problem with another technology you wanted to try out. 

Jon did some demos of specific technologies he had used this way of getting to know a new technology (webAPI, signalR and SPA). These demos were not supporting points about learning super well, but I found the investment analogy very useful and it was over all a really good keynote.


<h2>Mostly webessentials with Mads Kristensen</h2>
I chose to go to <a href="https://twitter.com/mkristensen">Mads Kristensen</a>'s talk titled: <strong>Beyond Visual Studio 2012: What’s Coming for Web Developers</strong>. This talk was mostly technical on the new web dev support stuff in Visual Studio 2012 (for instance: page inspector, js call stack and js intellisence) and the really nice things in <a href="http://vswebessentials.com/">webessentials</a>. If you use Visual Studio 2012 for web development you really should install webessentials. 

My tweets from this session: 
<blockquote class="twitter-tweet"><p>OH: @<a href="https://twitter.com/mkristensen">mkristensen</a> at <a href="https://twitter.com/search/%23ddc13">#ddc13</a> "Jae, der er vist en bug i Sharepoint..." :D <a href="https://twitter.com/search/%23outofcontext">#outofcontext</a></p>&mdash; Steen H. Rasmussen (@steenhulthin) <a href="https://twitter.com/steenhulthin/status/319734070647078912">April 4, 2013</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p><a href="https://twitter.com/search/%23ddc13">#ddc13</a> @<a href="https://twitter.com/mkristensen">mkristensen</a> "internal only" ?? <a href="http://t.co/a92JhSrvUJ" title="http://bit.ly/ZbGWlo">bit.ly/ZbGWlo</a></p>&mdash; Steen H. Rasmussen (@steenhulthin) <a href="https://twitter.com/steenhulthin/status/319734584575156224">April 4, 2013</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p>OH @<a href="https://twitter.com/mkristensen">mkristensen</a> "på google... på Bing mener jeg selvfølgelig - nu skal jeg lige huske, hvor jeg er..."</p>&mdash; Steen H. Rasmussen (@steenhulthin) <a href="https://twitter.com/steenhulthin/status/319735411251503104">April 4, 2013</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<h2>SPA - Single Page Applications with Gudmundur Hreidarsson</h2>
<a href="https://twitter.com/gudmundurh">Gudmundur Hreidarsson</a>'s talk was titled <strong>Bevæg dig uden for din sikre zone – lav single page apps</strong>. The talk was a really good walk-through of what is needed to get from a MVC app to a SPA app. The main points: SPA is fun, but remember to clean up after yourself (no garbage collection in javascript or automatic elimination of ghost events). 
Gudmundur recommended looking at <a href="http://todomvc.com/">http://todomvc.com/</a> to get an idea of how a todo app could be implemented in many different SPA frameworks. <a href="http://durandaljs.com/">http://durandaljs.com/</a> was used for building the app. 
The code for the SPA is on Gudmundur's <a href="https://github.com/gudmundurh/DDCMiniSpiir">github page</a>

<h2>Async and Rx with Kasper Holdum</h2>
The next talk I went to was about the async (the keyword) and the Reactive extension (Rx) by Kasper Holdum. The talk was good, but could have use diagram on how async and Rx fits in on top on/in the .NET framework. The talk was very code centric it was a nice intro to Rx and async to me. However from some of the questions it seems like it was a little confusing what async and Rx was respectively. 

<h2>Advanced Unittesting with Mark Seemann</h2>
For the last talk with technical content I decided to go to <a href="https://twitter.com/ploeh">Mark Seemann</a>. A choice I wasn't going to regret. Mark presented a number of patterns for test setup and assertion. The patterns were a mix between good oldies from <a href="http://xunitpatterns.com/">Gerard Meszaros book</a> with some variation and some patterns I hadn't seen before like using a DI container for object creation in the setup. A very good talk indeed.

One thing that continues to surprise me though is that the question from the audience "Is it worth it?" comes up very often at talks on unittesting. Often it sounds to me like the questioner really want to hear "No, it's not worth it." and feel better about not doing unittesting. I say if you don't want to unittest then don't. Don't ask for forgiveness, it's ok - just make it a conscious decision. Either because you don't want to invest in learning to unittest or because you just don't want to do it in your specific project. (Mads Kristensen said in his talk that he doesn't have unittests in webessential so some people can make great software without unittests.) 

<h2>Final keynote by Christian Birch</h2>
For some reason the second keynote, <a href="https://twitter.com/christian_birch">Christian Birch</a>, was not announced in the program. Christian Birch is co-founder of <a href="https://etilbudsavis.dk/">etilbudsavis.dk</a>. He basically told the story about how etilbudsavis.dk came about. etilbudsavis.dk had 400.000.000 pageview in 2012, which makes it a significant player in the Danish app marked. Inspiring to see startup started by two young guys can really become something very successful. 


<h2>Final Words</h2>
Overall a good conference. The focus on specific MS technologies were a bit too much for me taste though. I prefer conferences that are not too vendor specific even though the talks that are technology agnostic. But I should most likely have gone to a codecamp in stead to get more community/mingling focus. Really everything was arranged professionally and the conference team did a good job. 

<strong>Good:</strong> 
Content generally really good, Danish speakers (well a bit strange, but probably bring some other mice out of their holes, compared to the normal international conferences. ) and everything ran smoothly. 

<strong>Room for improvement:</strong> 
I missed places to sit and eat. I really would have liked more possibilities to mingle. The talks were 1 hour and 15 minutes, which I find a too long. I think one hour is generally enough to make the brain boil. I would suggest a either longer breaks or a long lunch break where speakers and other attendees have the possibility to show some of their own projects. This would require a setup with more tables and plug for charging computers/phones, but for me that would transform the conference from something that resembles a Microsoft showcase to something that resembles a Microsoft community event.