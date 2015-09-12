# tng_wordcloud
Code for getting TNG transcripts and building a word cloud.  The main work horse is the excellent word cloud generator found at:
  https://github.com/amueller/word_cloud
For instructions on how to install it, please visit his website.

This code also makes use of the modules matplotlib, nltk, and scipy.

This iPython notebook consists of the following functions:
  get_transcripts(output_dir):
    Grab all of the html files on http://www.chakoteya.net for the Star Trek: TNG series and save them in the directory specified by output_dir.

  get_lines(parse_file_function):
    Parse each line in all the html files using the parse_file_function.  This function should return a list of lines.

  get_two_word_phrases(lines, output_filename):
    Create a dictionary of dictionaries that contains counts for all two word phrases.

  get_word_counts(lines):
    Get single word counts of all words in the corpus.

  write_sorted_words(word_dict, out_filename):
    Helper function to write the output of get_word_counts in sorted order.

  make_word_cloud():
    Actually create the word cloud.

Run the following commands:

  all_lines = get_lines("script_dir", get_all_lines)
  word_counts = get_word_counts(all_lines)
  write_sorted_words(word_counts, out_filename="all_cast_words.txt")
  get_two_word_phrases(all_lines, out_filename="two_word_phrases.txt")


This will produce two text files, "all_cast_words.txt" and "two_word_phrases.txt".  You will then probably want to
do a lot of manual editing of these word lists until you get something you like. Suppose you have created a file
"sorted_cloud_words.txt" consisting of all the words you want to use in your word cloud. Then run the command:

  make_wordcloud("sorted_cloud_words.txt", "tng_emblem.png", "TNG_Title.ttf")

The word cloud has a bit of randomness, so running it multiple times will give you different results.

