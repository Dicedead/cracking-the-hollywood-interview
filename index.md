---
layout: generic
---
# Why it is important to prepare before an interview
**TODO rewrite intro**
On average, the production of a major box office movie costs $65 million, without counting the marketing and distribution fees. Unlike house construction, which usually ends up exactly like the pre-sketched plan, making a movie is unpredictable and anticipating the audience’s opinion is nearly impossible despite the effort and money spent.

Thus, producing a movie the right way is a crucial job that requires long studies and decision-making about the relevant parts that define the film. This includes the storyline, the script, the actors, the budget, and many more features.

This motivates our goal of studying the successful and failed films in terms of public ratings (collected through the IMDb database) and box office revenue. We mainly analyze the different characteristics that define a movie in order to come up with a set of criteria that, if present, will more likely make a movie successful. Additionally, since a high rating might not necessarily imply high revenue, we will investigate how to optimize each metric independently.

Usually movie making interview questions target the following topics: 
* The country where the movie should be made in.
* The actors that should play in the movie.
* How to write the movie plot.

**TODO introduce dataset ?**

# Country

{% include rev_map.html %}
{% include rat_map.html %}

# Actors
Choosing actors for a successful movie is an important decision that can have a significant impact on the final product. Here are a few factors to consider when selecting actors for your movie:

## Gender
Usually people tend to say that there is no one "right" answer when it comes to choosing actors based on their gender for a successful movie. However, studying the effect of actor genders on the revenue and rating gave interesting results.
The aim of this part is to perform a linear regression on the movies box office revenue and rating. We want to investigate the degree to which the actor's gender predicts the change of the movie revenue and rating. 
The following plots show the regression coefficient for males and females, which represents the contribution to the revenue and rating respectively.
{% include gender_influence_revenue.html %}
{% include gender_rating_influence.html %}
As we can see, men tend to have higher contribution on the success than women. This is more emphasized on the rating than revenue.
## Age
The actor's age may is one of several factors that can influence a movie's success. For example, an actor who is very young or very old may bring a certain level of credibility or gravitas to a role that helps to make the movie more successful. On the other hand, an actor who is in the prime of their career may be more physically capable of performing action scenes or other demanding roles, which could also contribute to the success of a movie.
The following plot helps getting more insight on how the movie's revenue and rating change with respect to the actor's age.
{% include avg_revenue_rating_age.html %}
## Character types
{% include rating_revenue_per_char_type.html %}

## Interactions between actors

How do actors interact with each other? Clearly, Will Smith and Chris Rock do not get on well. But what about the others? We have gathered the castings of films and created a graph representing the interactions between actors. Nodes represent actors and edges "has worked with"-relationships. Edges are weighted in terms of the number and success of collaborations between two people. Each time two actors played in the same film, the revenue or rating of that movie is added to the weight. 

We set up a graph for each genre containing the casting of the 1000 most successful films in that category. In some cases, there may be groups of actors who usually work together, because of directors' preferences, previous successful films, good synergies, etc. To observe if there exist clusters in the graph, we apply the Louvain algorithm. Let's take a look at the 'drama' graph!
{% include ./network_test/index.html %}


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
