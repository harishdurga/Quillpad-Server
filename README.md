# Quillpad Transliteration Server

   Quillpad is an indic language input technology that revolutionized the Indian language typing scene. It is one of the most popular Indic input technologies with more than a billion words typed on the website alone.

   > Quillpad pioneered the successful use of machine learning for 
   > building a predictive language input technology. 
   > Quillpad has been rated as the best by many organisations that have embraced Quillpad.

   ### Version
   1.0.1

   ### Preparation

   There are several archive files in the repository which have to be extracted, these include trained transliteration models and additional text files necessary for the Quillpad Server

   *  CherryPy-3.2.2.tar.gz
   *  EnglishPronouncingTrees.tar.bz2
   *  IndianPronouncingTrees.tar.bz2
   *  additional_text_files.zip
   *  bengali.tar.bz2
   *  gujarati.tar.bz2
   *  hindi.tar.bz2
   *  kannada.tar.bz2
   *  malayalam.tar.bz2
   *  marathi.tar.bz2
   *  nepali.tar.bz2
   *  punjabi.tar.bz2
   *  tamil.tar.bz2
   *  telugu.tar.bz2
   *  unique_word_files.zip

   Kindly extract all of these archives into the repository folder itself.

   ### Installation

   Quillpad Server requires [Python 2.7](https://www.python.org/downloads/) to run.

   Before we can compile, we need to install few other things
   ```sh
   $ sudo apt-get install python-dev
   $ sudo apt-get install -y python-pyrex
   $ sudo apt-get install python-pip
   $ pip install CherryPy
   ```
   
   
   First, we need to compile the Quillpad Model loader that will be used to load the trained transliteration models

   ```sh
   $ cd Python\ Cart/python
   $ python setup.py build_ext --inplace
   $ cp QuillCCart.so ../../
   $ cd ../../
   ```
   Before we can run the server we need to extract some files
   ```sh
   $ unzip unique_word_files.zip additional_text_files.zip
   $ tar -xf bengali.tar.bz2 EnglishPronouncingTrees.tar.bz2 gujarati.tar.bz2 hindi.tar.bz2 IndianPronouncingTrees.tar.bz2 kannada.tar.bz2 malayalam.tar.bz2 marathi.tar.bz2 nepali.tar.bz2 punjabi.tar.bz2 tamil.tar.bz2 telugu.tar.bz2
   ```

   Now, the Quillpad Server is ready to run

   ```sh
   $ python startquill_cherry.py
   ```

   ### Additional Information

   * Quillpad runs on port number 8090 (Additional configuration parameters are in *quill_cherry8088.conf*)

   * *processWordJSON* and *processWord* are the API endpoints over which the transliteration server can be accessed.
   > Example:

      * localhost:8090/processWordJSON?inString=hello&lang=hindi
      * localhost:8090/processWordJSON?inString=hello&lang=kannada

   ### Development

   Additional Quillpad Documentation coming soon. Thanks for your patience.
