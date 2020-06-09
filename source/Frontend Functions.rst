Front End
=========

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
   
