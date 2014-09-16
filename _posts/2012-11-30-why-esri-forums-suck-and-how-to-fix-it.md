---
layout: blogpost
title: Why Esri Forums suck (and How to Fix It)!
lastupdated: 2014-09-16
---
#Why Esri Forums suck (and How to Fix It)!

[Esri][1] has a number of [forums][2] where the ArcGIS/esri community and esri employees can help with questions on esri software. That is all a good idea. The problem however is that it doesn't really work. 

In the past esri forums were in layout and functionality just a pure forum. Here's an [example][3]. That didn't work very well (for me at least). Finding the answer in a thread was really a pain. Some of these threads went on for pages and the answer *would* be anywhere in the thread *if* the question was answered. 

Generally a forum is good for general questions or question with no right answer and an answer can really just be an opinion. Like [politicsforum][4] - perfect for a forum. But the ArcGIS users/community are technical people on a mission to solve a technical problem with their esri software, thus will *NOT* start a thread with a discussion on when [Jack Dangermond][5] will retire as company president. They would be helped much better with a Q&A site. A Q&A site is perfect for when you have specific question which has a specific answer. 

Esri then changed the forums to have up- and downvoting and accepted answer similar to [stackoverflow][6]. Ok, better, but what esri do not seem to realize is that there is also another thing that is necessary for a Q&A site to work. Using it as a Q&A site. 

So what do I mean by that: 

*   Answer the question that is asked! (seem obvious but wait for it)
*   One (1!) question per thread. Esri users and employees seem to have growth very used to the forum style. 

Let's see an example: I posted [this question][7] to the esri forum (after not getting any answer on [gis.stackexchange.com][8]). 

***Question:*** 

> ## Applying schema changes on a esri geodatabase two-way replica set 
>
>I have an Esri geodatabase two-way replica set. I need to update the schema on both databases in the replica set. Esri describes doing this using ArcGIS schema tools (compare/export/import replica schema - see [here][9]). 
>I have control of both databases in the replica set and I would prefer to make a python script, which updates the schema and run that on both databases in the replica set. Are there potential problems with applying the schema changes to both databases instead using Esri's schema tools? 

I got this ***answer:*** 

> Please see the below link for schema changes Best Practices. It states " In general, it is best to avoid schema changes. Schema changes can lead to inconsistencies among replicas, and the extra task of applying schema changes can increase performance costs. However, there are cases when schema changes must be applied". [ http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//00270000003w000000.htm][10] If it is absolutely necessary to change schema on replica data then please follow the procedure of export, compare and import schema changes tool. In this workflow, you can avoid duplication of your effort and maintain consistency in both parent and child geodatabase. Hope this clarifies your queries. 

Ok, let's see; does this answer the question? Well, no. It does not go into any potential problems with the schema update outside the esri tools. It repeats what is in the documentation (which was actually the root of the question). A "real" answer would tell why it would be a problem not to use the esri tools. Ok, so a low quality answer - downvote and/or comment - unfortunately esri forums don't allow me to do either. 

You might argue that this is just one question, but I think this is no exception. Often I see answer (by esri employees) of low quality or not really answering the question. I appreciate the time put into the answer but I would rather *not* have an answer than a low quality one. 

** It turns out that changing the schema as suggested in the question in my case works fine - I did a fair amount of testing. I don't know if this is true for all cases though. ** 

Shortly after ***this post ticks in on the thread*** from a new person: 

> Reading about the process and Geoprocessing Tools available for this type of replica schema change synchronization in the Help, will there be / is planned any future role of X-Ray for ArcCatalog in this type of process when X-Ray is updated to support enterprise geodatabases?: X-Ray for ArcCatalog (ArcGIS 10) (Blog) [I omitted the link - it really doesn't matter for my point] Introduction to X-Ray for ArcCatalog (Video) [I omitted the link - it really doesn't matter for my point] 

Followed by ***this answer from the original answerer:*** 

> No information available at this moment of X-ray for enterprise geodatabase. Please put your suggestion on Idea site "http://ideas.arcgis.com/" which has more chance of quick consideration if more people vote for this idea. 

Now this thread just got hijacked. We have 2 questions in the thread. The forum heritage shows its ugly face. These last two posts do not even closely present an answer to the original question. It is just plain noise. It could be fixed easily by simply deleting the second question and the related answer and putting it into its own thread. This could be done by a moderator - for instance a Q&A trained esri employee.   

But what can esri make this better?! On the technical side: 

1.  Let the first post be THE ONLY question in the thread
2.  Allow comments 

On the community side: 

1.  Help making the site into a Q&A site through moderation - stop forum-like chatter noise
2.  esri employees have unique knowledge about the product - use that combined with training in how to use a Q&A site - magic could happen! To sum it up: be more like 

[gis.stackexchange.com][11]. Or move all new threads to gis.stackexchange.com.

 [1]: http://www.esri.com/ "esri"
 [2]: http://forums.arcgis.com "esri forums"
 [3]: http://forums.esri.com/Thread.asp?c=93&f=1148&t=298305 "esri old style forum"
 [4]: http://www.politicsforum.org/forum/ "politicsforum"
 [5]: http://en.wikipedia.org/wiki/Jack_Dangermond "Jack Dangermond"
 [6]: http://stackoverflow.com "stackoverflow"
 [7]: http://forums.arcgis.com/threads/72183-Applying-schema-changes-on-a-esri-geodatabase-two-way-replica-set
 [8]: http://gis.stackexchange.com/questions/39311/applying-schema-changes-on-a-esri-geodatabase-two-way-replica-set
 [9]: http://webhelp.esri.com/arcgisdesktop/9.3/index.cfm?TopicName=Applying_schema_changes
 [10]: http://help.arcgis.com/en/arcgisdesktop/10.0/help/index.html#//00270000003w000000.htm
 [11]: http://gis.stackexchange.com/