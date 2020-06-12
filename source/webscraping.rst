Webscraping
============


Below are function definitions used to perform the webscraping from youtube and the respective test functions   



.. py:function:: get_vid_data(folder,file):

   
   For each video in a list in a file, scrape the video name, description, number of likes, number of dislikes, date posted, and number of view.

   
   :param str folder: folder where files are stored with video link information, i.e - 'cooking'
   :param str file: file name of file holding the video links
   :return: data frame of scraped data for all videos
   :rtype: df : pandas DataFrame
   :raises TypeError: if folder or file is not a basestring


.. code-block:: python

   >>> get_videeo_links('cooking', 'bgfilms.txt')
   >>> Link 1 of 180.
       Link 2 of 180.
       Link 3 of 180.
       ...
       Link 180 of 180.
                                                    title          date   likes  dislikes    views                                        description
   0                     Coffee Cake | Basics with Babish  May 14, 2020   58024       558  3695756  This video is sponsored by Trade Coffee. Get 3...
   1    Binging with Babish: Lil' Bits from Rick and M...  May 12, 2020  113244      1385  8213638  Rick and Morty is back and it's Ricker and Mor...
   2                         Gnocchi | Basics with Babish   May 7, 2020   68519       491  3695756  Head to http://bit.ly/squarespacebabish to sav...
   3    Binging with Babish: Margaritas from Archer (f...   May 5, 2020   58874       415  2071377  This week, H Jon Benjamin, the voice of Sterli...
   4                      Pan Sauces | Basics with Babish  Apr 30, 2020   55737       492  5634594  Get 50% OFF your first 6-bottle box: https://b...
   ..                                                 ...           ...     ...       ...      ...                                                ...
   175           Binging with Babish: Pizza from Deadpool  Jun 19, 2018   99661      1535  2955816  Wade Wilson knew exactly what he was doing whe...
   176                       Burgers | Basics with Babish  Jun 14, 2018  116840      1860  3412617  Enter offer code “Babish” at Squarespace.com f...
   177  Binging with Babish: Pasta Puttanesca from Lem...  Jun 12, 2018   92043      1062  4138144  Pasta puttanesca can mean many things - a bond...
   178                  Risotto | Basics with Babish Live   Jun 8, 2018    2889       440  2828984  Every other week, cook-a-long with me on Twitc...
   179    Binging with Babish: Cannoli from The Godfather   Jun 5, 2018   82324       732  3088100  Check out some summer-adventure-recipe-videos ...

   



.. py:function:: get_links(user, t):

   Gets video links user

   :param str user: creator's username i.e. - 'bgfilms'
   :param char t: type of content creator i.e. 'u' - user, 'p' - playlist, 'c' - channel
   :return: list of links to videos
   :rtype: videolist : list   
   :raises TypeError: if user or t is not a basestring 
   :raises TypeError: if length of t is not equal to 1
   :raises assertionError: if t is not equal to 'u', 'p', 'c'

Below is an example code of how to use get_links
  
.. code-block:: python
   
   """
   The following code gets video links for user, type when called on terminal
   """
   from scraping.get_videeo_links import get_links
   from selenium import webdriver
   from bs4 import BeautifulSoup as bs
   import time

   
   SRC_DIR = './data/source_links/'
   
   fd = open('scraping/users.txt','r')
   r = fd.read().splitlines()
   fd.close()

   for item in r:

      user = item.split()[0]
      t = item.split()[1]
      g = item.split()[2]

      links = get_links(user, t)
      fd = open(SRC_DIR+g+'/'+user+'.txt','w+')
      fd.write('\n'.join(links))
      fd.close()
      print("Number of links :", len(links))


   
.. py:function:: test_get_video_data():
   
   Pytest test for get_vid_data function

   :raises assertionError: if d.columns do not all contain 'title','date','likes','dislikes','views','description'
   :raises assertionError: if d.title is not equal to 'Group 48 Video Presentation'
   :raises assertionError: if d.date is not equal to 'Mar 19,2020'
   :raises assertionError: if d.description is not equal to 'Group 48 video presentation for UCSD ECE271B Winter2020.'

.. py:function:: test_get_video_links():

   Pytest test for get_links function

   :raises assertionError: if links does not equal 'https://www.youtube.com/watch?v=2tDmuNu_1FQ'

