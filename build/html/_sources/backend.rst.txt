back end
========

.. py:function:: get_vid_data(folder,file):

   
   For each video in a list in a file, scrape the video name, description, number of likes, number of dislikes, date posted, and number of view.

   
   :param str folder: folder where files are stored with video link information, i.e - 'cooking'
   :param str file: file name of file holding the video links
   :return: data frame of scraped data for all videos
   :rtype: df : pandas DataFrame
   :raises TypeError: if folder or file is not a basestring

   
