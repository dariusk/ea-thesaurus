# ea-thesaurus

The [Edinburgh Associative Thesaurus](http://www.eat.rl.ac.uk/) (EAT) is a set of word association norms showing the counts of word association as collected from British university students around 1970. It's a weird set of associations very particular to its time and place (the second most popular result for "hello" is "dolly", which I doubt would happen today), but it's a fun little data set to play around with.

This data was ported to JSON format by Darius Kazemi in April 2015. He does not own or maintain the data. See the License information below for details.

Words are normalized to upper case. Here's an example of how you'd access the data in JavaScript. It'll be similar in other languages:

```javascript
// assuming you loaded the json into a variable called "thesaurus"

console.log(thesaurus['HELLO']);
/*
[ { 'GOOD-BYE': '56' },
  { DOLLY: '8' },
  { CHEERIO: '5' },
  { GREETING: '3' },
  { HI: '3' },
  { THERE: '3' },
  { AGAIN: '2' },
  { FRIEND: '2' },
  { HELLO: '2' },
  { BOY: '1' },
  { CHEERFUL: '1' },
  { GOOD: '1' },
  { LOOK: '1' },
  { MAN: '1' },
  { MARIAN: '1' },
  { MEETING: '1' },
  { MORNING: '1' },
  { PLUM: '1' },
  { SMILE: '1' },
  { WHERE: '1' },
  { WORLD: '1' } ]
*/
```

This returns a list of words that subjects associated with the source word ("hello" in this case), along with the frequency of responses. So in this case, 56 people associated "good-bye" with "hello". The result is always sorted in descending order by frequency, then ascending alphabetically where frequencies are equal. So `thesaurus[word][0]` will *probably* return the most common word association, but it also might be tied two or more ways. Worth double checking when parsing/using the data.

From the official documentation:

>The Edinburgh Associative Thesaurus is a database of word association norms. The traditional way to collect word association norms is to show or say a word to several people and ask them to say the word which first comes to their minds upon receiving the stimulus. The link established between the stimulus and the response is not semantically labelled (e.g. as synonym, antonym or by a case relation) and can only be regarded as an association. These associations can be viewed as a list, but convey more if represented as a network. Such networks can be constructed from the list by a variety of methods including multi- dimensional scaling, clustering and graph theoretic representation using the association values to represent probabilities of stimulus-response association.

>The Edinburgh association norms were collected by growing the network from a nucleus set of words. Responses were collected to words in this nucleus set, then these responses were used to obtain further responses, and so on. In fact the cycle was repeated about three times since by then the number of different responses was so large that they could not be re-used as stimuli. Data collection stopped when 8400 stimulus words had been used. Each stimulus word was presented to 100 different subjects, each of whom received 100 words. This gave rise to a total of 55732 nodes in the Thesaurus network.

>The subjects were mostly undergraduates from a wide variety of British universities. The age range of the subjects was from 17 to 22 with a mode of 19. The sex distribution was 64 per cent male and 36 per cent female. The data was collected between June 1968 and May 1971.

## License
The Edinburgh Associative Thesaurus dataset is public sector data available under an [Open Government License](http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/). As such you are free to

* copy, publish, distribute and transmit the Information;
* adapt the Information;
* exploit the Information commercially and non-commercially for example, by combining it with other Information, or by including it in your own product or application.

See the [Open Government License](http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/) for further detail.
