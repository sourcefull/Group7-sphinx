Front End
=========

Function for front-end part I is given as below.
.. py:function:: wordscloud(x,Genre):

   
   This function is to plot word cloud over all time.

   
   :param Timestamp x: Input timestamp from the slider which indicates the time of the word cloud
   :param str Genre: scalar depicting the genre of the content: "cooking", "gaming", "influencers"
   :return: None, but a word cloud should be shown in the graph
   :rtype: None
   :raises TypeError: none

Function for front-end part II is given as below.
.. py:function:: P_N_cloud(x,Genre):

   
   This function is to plot word cloud for both positive and negative over all time.

   
   :param Timestamp x: Input timestamp from the slider which indicates the time of the word cloud
   :param str Genre: scalar depicting the genre of the content: "cooking", "gaming", "influencers"
   :return: None, but a word cloud should be shown in the graph
   :rtype: None
   :raises TypeError: none

Below are function definitions used to perform the front end part three
Function analyze_text_color

.. py:function:: analyze_text_color(text, genre, metric):

   
   Analyze the given text and produce color labels for the words 

   
   :param str text: scalar depicting the text that needs to be analyzed
   :param str genre: scalar depicting the genre of the content: "cooking", "gaming", "influencers"
   :param str metric: scalar depicting the metric to base the analysis on: "likes_mean", "likes_median", "dislikes_mean", "dislikes_median", "views_mean", "views_median", "polarity", "subjectivity"
   :return: a list with the same number of elements as number of words in given text, with each corresponding element being the color for that word: "red" means bad, "yellow" means okay, "green" means good and "white" means "Not found" (in database)
   :rtype: list
   :raises TypeError: none
   
Function color_changer

.. py:function:: color_changer(x,Genre,Metric)
   
   change the color of input text instantly
   
   :param str x: scalar depicting the text that needs to be analyzed
   :param str genre: scalar depicting the genre of the content: "cooking", "gaming", "influencers"
   :param str metric: scalar depicting the metric to base the analysis on: "likes_mean", "likes_median", "dislikes_mean", "dislikes_median", "views_mean", "views_median", "polarity", "subjectivity"
   :return: none
   
