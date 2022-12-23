---
layout: generic
---
# Why it is important to prepare before a movie pitch
**TODO rewrite intro**
On average, the production of a major box office movie costs $65 million, without counting the marketing and distribution fees. Unlike house construction, which usually ends up exactly like the pre-sketched plan, making a movie is unpredictable and anticipating the audience’s opinion is nearly impossible despite the effort and money spent.

Thus, producing a movie the right way is a crucial job that requires long studies and decision-making about the relevant parts that define the film. This includes the storyline, the script, the actors, the budget, and many more features.

This motivates our goal of studying the successful and failed films in terms of public ratings (collected through the IMDb database) and box office revenue. We mainly analyze the different characteristics that define a movie in order to come up with a set of criteria that, if present, will more likely make a movie successful. Additionally, since a high rating might not necessarily imply high revenue, we will investigate how to optimize each metric independently.

Usually movie making pitch questions target the following topics: 
* The country where the movie should be made in.
* The genre of the movie.
* The actors that should play in the movie.
* The movie's plot.

**TODO introduce dataset ?**

# Country
Let's start with where you should make and release your movie. 

In terms of revenue, there is a balance between production expenses and clientele to be found. Indeed:
{% include rev_map.html %}
Of course, the USA is a top scorer in this regard with 324k. The English-speaking worldwide audience also helps develop Australian and British movies, with comparable revenues. But there are a few surprises! Peru, with a staggering 550k mean revenue, has been home to a few box office successes such as _Anaconda_ starring Jennifer Lopez and _The Specialist_ starring Sylvester Stalone, both films with relatively small budget largely thanks to the small production costs in Peru, but large worldwide audiences. The same goes for Thailand, which is notably home to the James Bond movie _Thunderball_. Inversely, the language barrier is what stops Bollywood movies from making it to worldwide cinemas and capitalizing on small directing budget in India. 

When examining the mapping between countries and mean ratings, we find our first major discrepancy between the features optimizing for revenue and those optimizing for rating:
{% include rat_map.html %}
All previously cited monetary film successes received poor ratings. For instance, _Anaconda_ received 4.8/10. This might also be because it is a horror movie, as we will see later. One could think countries scoring high on rating are big on the World genre, but that is not necessarily true: the award winning drama movie _Pinjar_ was shot in Pakistan, and the crime-drama-thriller _Z_ shot in Algeria was nominated for awards.

# Genres
How do rating and revenue vary as a function of the genre?
{% include genres_scatter_plot.html %}
In short: to maximize rating, go for a documentary, and to maximize revenue, go for a family film!

Of course, much more can be said. Genres are visibly clustered on the scatter plot. One can expect similar rating and revenue among the following groups:
* Drama, crime-fiction, LGBT, biography and comedy-drama for a mean rating around 6.3 and revenue just under 200k;
* Romantic comedy and romantic drama, as well as action/adventure and thriller with a rating close to 6 but revenue around 250k;
* etc.

A word of caution: movie genres are often arbitrarily attributed, thus it is unclear what distinguishes a genre from another. This can have drastic consequences on rating and revenue. For example, the boundary between family drama and romantic drama can be blurry, yet family drama movies are two thirds less profitable than romantic drama movies. There are more precise elements defining a movie, like its cast.


# Actors
### Why is it important to wisely choose your cast?
<img src="actors.jpeg"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />


Choosing actors for a successful movie is an important decision that can have a significant impact on the final product.
Actors are trained to portray a variety of characters and can play different roles in different productions. Acting is a craft that requires skill in understanding and interpreting different characters and their motivations, as well as the ability to convey those characters through speech, movement, and facial expressions. Actors may play different roles in theater, film, television, or other media, and may portray characters of different ages, genders, and cultural backgrounds. Some actors are known for their versatility and are able to play a wide range of characters, while others may specialize in a particular type of role or genre. This motivates our study to find patterns on which type of actors is best suited for a given movie.  
Here are a few factors to consider when selecting actors for your movie:

## Gender
Usually people tend to say that there is no one "right" answer when it comes to choosing actors based on their gender for a successful movie. However, studying the effect of actor genders on the revenue and rating gave interesting results.
The aim of this part is to perform a linear regression on the movies box office revenue and rating. We want to investigate the degree to which the actor's gender predicts the change of the movie revenue and rating. 
The following plots show the regression coefficient for males and females, which represents the contribution to the revenue and rating respectively.
{% include gender_influence_revenue.html %}

As we can see, men tend to have slightly higher contribution on the revenue than women. 

{% include gender_rating_influence.html %}

## Age
The actor's age is one of several factors that can influence a movie's success. For example, an actor who is very young or very old may bring a certain level of credibility or gravitas to a role that helps to make the movie more successful. On the other hand, an actor who is in the prime of their career may be more physically capable of performing action scenes or other demanding roles, which could also contribute to the success of a movie.
The following plot helps getting more insight on how the movie's revenue and rating change with respect to the actor's age.
{% include avg_revenue_rating_age.html %}

## Character types
Characters are a crucial element of any movie, as they help to drive the story forward and provide a connection for the audience. Strong characters can contribute significantly to the success of a movie by engaging the audience and making them care about what happens to the characters. 

### Sentiment analysis
Sentiment analysis, also known as opinion mining, is a field of natural language processing that involves analyzing text data to determine whether it conveys a positive, negative, or neutral sentiment. We used this technique to measure the sentiments of the character types embodied in movies. The analysis returns a sentiment score that is a value between -1 and 1, where -1 is very negative, 0 is neutral and 1 is very positive. 
For example:
* "arrogant kungfu guy" yields a negative sentiment due to the presence of the word "arrogant"  
Indeed, some audiences may prefer positive characters who are likable and heroic, while others may be more drawn to complex and flawed characters who are more realistic and relatable. To have better insight, we have plotted the sentiment score of 72 character types drawn from tvtropes.com as well as the median rating and revenue of the movies they were envolved in.

{% include rating_revenue_per_char_type.html %}

We can see that most of the character types tend to have a neutral sentiment. Also, those types were envolved the movies with the highest revenue and rating. However, TODO

## Interactions between actors
How do actors interact with each other? Clearly, Will Smith and Chris Rock do not get on well. But what about the others? We have gathered the castings of films and created a graph representing the interactions between actors. Nodes represent actors and edges "has worked with"-relationships. Edges are weighted in terms of the number and success of collaborations between two people. Each time two actors played in the same film, the revenue or rating of that movie is added to the weight. 

We set up a graph for each genre containing the casting of the 1000 most successful films in that category. In some cases, there may be groups of actors who usually work together, because of directors' preferences, previous successful films, good synergies, etc. To observe if there exist clusters in the graph, we apply the Louvain algorithm. Let's take a look at the 'drama' graph!


Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
