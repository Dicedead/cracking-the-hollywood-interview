---
layout: generic
---
# Why it is important to prepare the Hollywood interview
Let's say you are already bored of cracking the coding interview. You have crushed all your interviews at Big Tech companies and want new challenges. For that reason, you have an interview next week with a Hollywood executive producer where you will conceptualize a new movie. You have to come up with a film from scratch but you don't know where to start. This time, you have to carefully think about and explain your choices. There is a lot of money involved: on average, the production of a significant box office movie costs [$65 million](https://www.investopedia.com/financial-edge/0611/why-movies-cost-so-much-to-make.aspx), without counting the marketing and distribution fees.

> It is brain surgery! It is bloody brain surgery! You’re putting together a whole group of people, you’re trying to budget as accurately as you can and, at the end of it, you’ve got to sell a lot of tickets. That’s more complex than banking ...I’m not kidding myself: I love the challenge. If you don’t, don’t do the job.
>
> -- <cite>Ridley Scott</cite>

There are many challenges that can make it difficult to produce a good movie. Some of the main questions include finding a compelling, well-written story that can engage and entertain the audience, assembling a talented cast, etc. We present some of the most common challenges identified by filmmakers in a [survey](https://shortmovie.club/filmmaker-challenge/) in 2019.

{% include pie.html %}

We have studied a large dataset of movies and actors to analyze what makes a movie successful in terms of public ratings and box office revenue. We mainly analyze the different characteristics that define a movie to come up with a set of criteria that make it more likely for a movie to be successful.  Additionally, since a high rating may not necessarily imply a high revenue, we investigate how to optimize each metric independently. With that information, we will help you prepare the challenging Hollywood interview!

We will address the question of what makes a movie successful movie by analyzing the following four topics:
* The country where the movie is produced.
* The genre of the film.
* The plot.
* The cast of actors.

Let's dive in!

<img src="countries.png" width="100%"/>

Before making any conclusions, we want to mention that we have adapted the box office revenue of the films to the USA inflation rate corresponding to the year the movies were released. The Consumer Price Index (equivalent to inflation) reference corresponds to 1982. That way, we can compare films from different decades thanks to a similar monetary scale.

Now, let's start with where you should make and release your movie. 

In terms of revenue, there is a balance between production expenses and clientele to be found. Indeed:
{% include rev_map.html %}
Of course, the USA is a top scorer in this regard with $324k. The English-speaking worldwide audience also helps develop Australian and British movies, with comparable revenues. But there are a few surprises! Peru, with a staggering $550k mean revenue, has been home to a few box office successes such as _Anaconda_ starring Jennifer Lopez and _The Specialist_ starring Sylvester Stalone, both film with relatively small budgets largely thanks to the small production costs in Peru, but large worldwide audiences. The same goes for Thailand, which is notably home to the James Bond movie _Thunderball_. Inversely, the language barrier is what stops Bollywood movies from making it to worldwide cinemas and capitalizing on small directing budget in India. 

When examining the mapping between countries and mean ratings, we find our first major discrepancy between the features optimizing for revenue and those optimizing for rating:
{% include rat_map.html %}
All previously cited monetary film successes received poor ratings. For instance, _Anaconda_ got 4.8/10. This might also be because it is a horror movie, as we will see later. One could think countries scoring high on ratings are big in the World genre, but that is not necessarily true: the award winning drama movie _Pinjar_ was shot in Pakistan, and the crime-drama-thriller _Z_ shot in Algeria was nominated for awards.

<img src="genres.png" width="100%"/>

### How do rating and revenue vary as a function of the genre?
{% include genres_scatter_plot.html %}
In short: to maximize rating, go for a documentary, and to maximize revenue, go for a family film!

Of course, much more can be said. Genres are visibly clustered on the scatter plot. One can expect similar ratings and revenue among the following groups:
* Drama, crime-fiction, LGBT, biography and comedy-drama for a mean rating of around 6.3 and revenue just under 200k;
* Romantic comedy and romantic drama, as well as action/adventure and thriller with a rating close to 6 but revenue around 250k;
* etc.

A word of caution: movie genres are often arbitrarily attributed, thus it is unclear what distinguishes a genre from another. This can have drastic consequences on rating and revenue. For example, the boundary between family drama and romantic drama can be blurry, yet family drama movies are two thirds less profitable than romantic drama movies. There are more precise elements defining a movie, like its cast and plot. Let's analyze the latter now.

<img src="plots.png" width="100%"/>

When they come to the movie theater, viewers have some expectations regarding the movie's plot. These expectations are due to movies portraying the same kinds of events accross genres. Thus, for each genre, we have separated movies with high/low revenue and high/low rating; formally: the top and bottom 10% of movies for each metric, then we have run topic detection on their plot summaries to see what do successful/unsuccessful movies with respect to each metric display. Let's look at the results for a few genres!

<form>
	<input type="radio" id="iframe1_c" name="plot_radio" value="iframe1_c" checked>
	<label for="iframe1_c">Action by rating</label>
	<input type="radio" id="iframe2_c" name="plot_radio" value="iframe2_c">
	<label for="iframe2_c">Comedy by rating</label>
	<input type="radio" id="iframe3_c" name="plot_radio" value="iframe3_c">
	<label for="iframe3_c">Drama by rating</label>
	<input type="radio" id="iframe4_c" name="plot_radio" value="iframe4_c">
	<label for="iframe4_c">Romance by rating</label>
	<input type="radio" id="iframe5_c" name="plot_radio" value="iframe5_c">
	<label for="iframe5_c">Thriller by rating</label>
	<input type="radio" id="iframe6_c" name="plot_radio" value="iframe6_c">
	<label for="iframe6_c">Action by revenue</label>
	<input type="radio" id="iframe7_c" name="plot_radio" value="iframe7_c">
	<label for="iframe7_c">Comedy by revenue</label>
	<input type="radio" id="iframe8_c" name="plot_radio" value="iframe8_c">
	<label for="iframe8_c">Drama by revenue</label>
	<input type="radio" id="iframe9_c" name="plot_radio" value="iframe9_c">
	<label for="iframe9_c">Romance by revenue</label>
	<input type="radio" id="iframe10_c" name="plot_radio" value="iframe10_c">
	<label for="iframe10_c">Thriller by revenue</label>
</form>

<iframe id="iframe1_c" class="plot_options" src="plots/Acti_rating_succ_topic_1.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe1_c" class="plot_options" src="plots/Acti_rating_fail_topic_1.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe1_c" class="plot_options" src="plots/Acti_rating_succ_topic_2.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe1_c" class="plot_options" src="plots/Acti_rating_fail_topic_2.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe1_c" class="plot_options" src="plots/Acti_rating_succ_topic_3.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe1_c" class="plot_options" src="plots/Acti_rating_fail_topic_3.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>

<iframe id="iframe2_c" class="plot_options" src="plots/Come_rating_succ_topic_1.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe2_c" class="plot_options" src="plots/Come_rating_fail_topic_1.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe2_c" class="plot_options" src="plots/Come_rating_succ_topic_2.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe2_c" class="plot_options" src="plots/Come_rating_fail_topic_2.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe2_c" class="plot_options" src="plots/Come_rating_succ_topic_3.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe2_c" class="plot_options" src="plots/Come_rating_fail_topic_3.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>

<iframe id="iframe3_c" class="plot_options" src="plots/Dram_rating_succ_topic_1.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe3_c" class="plot_options" src="plots/Dram_rating_fail_topic_1.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe3_c" class="plot_options" src="plots/Dram_rating_succ_topic_2.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe3_c" class="plot_options" src="plots/Dram_rating_fail_topic_2.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe3_c" class="plot_options" src="plots/Dram_rating_succ_topic_3.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe3_c" class="plot_options" src="plots/Dram_rating_fail_topic_3.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>

<iframe id="iframe4_c" class="plot_options" src="plots/Roma_rating_succ_topic_1.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe4_c" class="plot_options" src="plots/Roma_rating_fail_topic_1.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe4_c" class="plot_options" src="plots/Roma_rating_succ_topic_2.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe4_c" class="plot_options" src="plots/Roma_rating_fail_topic_2.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe4_c" class="plot_options" src="plots/Roma_rating_succ_topic_3.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe4_c" class="plot_options" src="plots/Roma_rating_fail_topic_3.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>

<iframe id="iframe5_c" class="plot_options" src="plots/Thri_rating_succ_topic_1.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe5_c" class="plot_options" src="plots/Thri_rating_fail_topic_1.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe5_c" class="plot_options" src="plots/Thri_rating_succ_topic_2.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe5_c" class="plot_options" src="plots/Thri_rating_fail_topic_2.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe5_c" class="plot_options" src="plots/Thri_rating_succ_topic_3.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe5_c" class="plot_options" src="plots/Thri_rating_fail_topic_3.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>

<iframe id="iframe6_c" class="plot_options" src="plots/Acti_revenue_succ_topic_1.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe6_c" class="plot_options" src="plots/Acti_revenue_fail_topic_1.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe6_c" class="plot_options" src="plots/Acti_revenue_succ_topic_2.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe6_c" class="plot_options" src="plots/Acti_revenue_fail_topic_2.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe6_c" class="plot_options" src="plots/Acti_revenue_succ_topic_3.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe6_c" class="plot_options" src="plots/Acti_revenue_fail_topic_3.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>

<iframe id="iframe7_c" class="plot_options" src="plots/Come_revenue_succ_topic_1.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe7_c" class="plot_options" src="plots/Come_revenue_fail_topic_1.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe7_c" class="plot_options" src="plots/Come_revenue_succ_topic_2.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe7_c" class="plot_options" src="plots/Come_revenue_fail_topic_2.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe7_c" class="plot_options" src="plots/Come_revenue_succ_topic_3.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe7_c" class="plot_options" src="plots/Come_revenue_fail_topic_3.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>

<iframe id="iframe8_c" class="plot_options" src="plots/Dram_revenue_succ_topic_1.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe8_c" class="plot_options" src="plots/Dram_revenue_fail_topic_1.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe8_c" class="plot_options" src="plots/Dram_revenue_succ_topic_2.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe8_c" class="plot_options" src="plots/Dram_revenue_fail_topic_2.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe8_c" class="plot_options" src="plots/Dram_revenue_succ_topic_3.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe8_c" class="plot_options" src="plots/Dram_revenue_fail_topic_3.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>

<iframe id="iframe9_c" class="plot_options" src="plots/Roma_revenue_succ_topic_1.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe9_c" class="plot_options" src="plots/Roma_revenue_fail_topic_1.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe9_c" class="plot_options" src="plots/Roma_revenue_succ_topic_2.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe9_c" class="plot_options" src="plots/Roma_revenue_fail_topic_2.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe9_c" class="plot_options" src="plots/Roma_revenue_succ_topic_3.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe9_c" class="plot_options" src="plots/Roma_revenue_fail_topic_3.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>

<iframe id="iframe10_c" class="plot_options" src="plots/Thri_revenue_succ_topic_1.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe10_c" class="plot_options" src="plots/Thri_revenue_fail_topic_1.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe10_c" class="plot_options" src="plots/Thri_revenue_succ_topic_2.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe10_c" class="plot_options" src="plots/Thri_revenue_fail_topic_2.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>
<iframe id="iframe10_c" class="plot_options" src="plots/Thri_revenue_succ_topic_3.html" style="height: 500; width: 49%; float: left; " height="500" width="49%" align="left"></iframe>
<iframe id="iframe10_c" class="plot_options" src="plots/Thri_revenue_fail_topic_3.html" style="overflow: hidden; height: 500; width: 49%; " height="500" width="49%"  align="right"></iframe>


<script>
    // Get all iframes
    var iframes2 = document.getElementsByClassName("plot_options");

    // Function to show and hide iframes based on the selected radio button
    function showHideIframes2() {
    // Loop through all iframes
    for (var i = 0; i < iframes2.length; i++) {
        // Get the current iframe
        var iframe = iframes2[i];

        // Get the value of the selected radio button
        var selectedRadio = document.querySelector('input[name="plot_radio"]:checked').value;

        // If the value of the selected radio button matches the id of the current iframe, show it
        if (selectedRadio == iframe.id) {
        iframe.style.display = "block";
        }
        // Otherwise, hide it
        else {
        iframe.style.display = "none";
        }
    }
    }

    // Show the iframes initially
    showHideIframes2();

    // Add an event listener to the radio buttons to show and hide the iframes when the radio buttons are clicked
    var radios2 = document.getElementsByName("plot_radio");
    for (var i = 0; i < radios2.length; i++) {
        radios2[i].addEventListener("click", showHideIframes2);
    }
</script>

Take action films when compared by rating for example. The second most successful topic is set in the Batman universe, and the third one in the Bourne universe, two esteemed franchises both by critics and the public. It makes sense that they beat action stories with boats and ships, as mentioned in the third less highly rated topic, and plots about crooks, heists and gamblers. Note that Batman and Bond movies are also among the most successful topics in action in terms of revenue too!

Similar observations can be made for any genre - one should be aware of what works and what does not in each genre before making a movie, as the plot later determines characters and thus actors.

<img src="actors.png" width="100%"/>

### Why is it important to wisely choose your cast?

<img src="actors.jpeg"
     alt="Markdown Monster icon"
     style="display:block; margin-left: auto; margin-right: auto; " 
     width="25%" 
     height="25%" 
     />


The casting of actors is an important decision that can have a significant impact on the movie.
Actors are trained to portray a variety of characters and can play different roles in different productions. Acting is a craft that requires skill in understanding and interpreting different characters and their motivations, as well as the ability to convey those characters through speech, movement, and facial expressions. Actors may play different roles in theater, film, television, or other media, and may portray characters of different ages, genders, and cultural backgrounds. Some actors are known for their versatility and are able to play a wide range of characters, while others may specialize in a particular type of role or genre. This motivates our study to find patterns on which type of actor is best suited for a given movie.  
Here are a few factors to consider when selecting actors for your movie:

## Gender
Usually, people tend to say that there is no one "right" answer when it comes to choosing actors based on their gender for a successful movie. However, studying the effect of actor genders on the revenue and rating gave interesting results.
The aim of this part is to perform a linear regression on the movie's box office revenue and rating. We want to investigate the degree to which the actor’s gender predicts the change in movie revenue and rating. 
The following plots show the regression coefficient for males and females, which represents the contribution to the earnings and rating respectively.
{% include gender_influence_revenue.html %}

As we can see, men tend to have a slightly higher contribution to the revenue than women. One possible reason for this is that men may have been more visible in leading roles in the past due to the historical imbalance in the entertainment industry, which has been dominated by men. This has resulted in fewer opportunities for women to play leading roles, which may have contributed to the perception that men are more important to the success of a movie.

{% include gender_rating_influence.html %}

However, we notice that the audience doesn't seem to have a large bias on the actor's gender when rating movies. A reason may be that spectators usually focus on the movie content and the actor's performance rather than their gender. 

## Age
The actor's age is one of several factors that can influence a movie's success. For example, an actor who is very young or very old may bring a certain level of gravitas to a role that helps to make the movie more successful. On the other hand, an actor who is in the prime of their career may be more physically capable of performing action scenes or other demanding roles, which could also contribute to the success of a movie.
The following plot helps get more insight into how the movie’s revenue and rating change with respect to the actor's age.
{% include avg_revenue_rating_age.html %}

We fit a line to both revenue and rating distribution to have more information on how they evolve with the actor age.
{% include age_rating.html %}{% include age_revenue.html %}
We can make the following observations:
* **Rating :** Actors with either with ages approximately smaller than 10 and higher than 70 tend to contribute to a higher rating. This can be explained by the fact that the audience gets more impressed by a nice performance from actors with uncommonly young, and unsurpeingly satisfied by well experienced ones. Overall, the average rating encouters a small increase with respect to the age, which again confirms the tendency of preferring well known and experienced actors.
* **Revenue :** Regarding the revenue, we can see that overall the average revenue slightly decreases compared to the rating. A probable reason can be the fact that the studied movies and the films in general target mainly youths. This category of the population might relate more to actors who are closer to their own age and may be able to better understand the experiences and challenges depicted on screen. Moreover, they are exposed to actors through social media, music, and other mediums, which can make them more familiar and appealing. It is also possible that some young people might prefer young actors simply because they find them physically attractive. Thus, they tend to spend more money on buying tickets for this kind of movie. 

## Character types
Characters are a crucial element of any movie, as they help drive the story forward and provide a connection for the audience. Strong characters can contribute significantly to the success of a movie by engaging the audience and making them care about what happens to the characters. 

### Sentiment analysis
Sentiment analysis, also known as opinion mining, is a field of natural language processing that involves analyzing text data to determine whether it conveys a positive, negative, or neutral sentiment. We used this technique to measure the sentiments of the character types embodied in movies. The analysis returns a sentiment score that is a value between -1 and 1, where -1 is very negative, 0 is neutral and 1 is very positive. 
For example, "arrogant kungfu guy" yields a negative sentiment due to the presence of the word "arrogant".  
Indeed, some audiences may prefer positive characters who are likable and heroic, while others may be more drawn to complex and flawed characters who are more realistic and relatable. To have better insight, we have plotted the sentiment score of 72 character types drawn from tvtropes.com as well as the median rating and revenue of the movies they were involved in.

{% include rating_revenue_per_char_type.html %}

We can see that most of the character types tend to have a neutral or positive sentiment scores. Also, those types were involved in the movies with the highest revenue and rating. However, the rating variable seems to be quite uncorrelated to the sentiment since we can find pretty much all the types in both high and low means.

## Interaction between actors
How do actors interact with each other? Clearly, Will Smith and Chris Rock do not get on well. But what about the others? We have gathered the castings of films and created a graph representing the interactions between actors. Nodes represent actors and edges "has worked with"-relationships. The size of a node is proportional to its degree. Edges are weighted in terms of the number and success of collaborations between two people. Each time two actors played in the same film, the revenue or rating of that movie is added to the weight. 

We set up a graph for each of the 5 most popular genres. A graph contains the casting of the 1000 most successful films in that category. In some cases, there may be groups of actors who usually work together, because of directors' preferences, previous successful films, good synergies, etc. To observe how clusters are distributed in the graph, we apply the Louvain algorithm. Let's take a look at the 'drama' graph!

First, let's choose "Drama by revenue" among the options below. It contains the actors that have played in the top 1000 drama movies ranked by box office revenue. Have you watched _The Godfather_? If not, we strongly recommend you cancel all your activities for today and turn on the TV to watch this fantastic trilogy! But before that, finish reading this story, please!

That said, zoom in on the blue cluster at the centre of the graph. It is located below the grey-blue one and above the two green groups. There, you may notice the names of famous actors, such as Robert De Niro, Robert Duvall, Al Pacino and Diane Keaton. All of them appear in the _Godfather_ saga. The first film became the highest-grossing film ever in 1972, and the two sequels were very successful too. Similarly, this cluster also appears in the "Drama by ranking" graph, considering that the saga has also been one of the most acclaimed stories of all time! 

Going back to actors, we observe in that cluster the presence of Hollywood stars such as Robert De Niro. They have considerably higher degrees than other artists in the same cluster. For instance, when we click over small nodes, such as Chris Sarandon, we notice that they have interacted with few people and are usually from the same cluster. However, when we click over the node of De Niro, we can observe a large number of other artists he has cooperated with. He is a bridge between many groups of actors, as he has been a relevant actor in the industry for many decades, and even connects a cluster of different generations. 

We let you play with the different graphs for the most popular genres. Once you have chosen many parameters for your movie and now have to select a casting, you may find some inspiration from actors that have previously worked well together from the graphs. Or if you are obsessed with an actor, and no matter what he or she will be the protagonist of your film, you can search for their name and analyze their previous cooperations with other artists that could complete your cast!