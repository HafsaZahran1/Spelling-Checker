# Spelling-Checker
This repository contains a Python implementation of a spell checker class that uses a suitable data structure to store a given dictionary. The spell checker class provides three main operations: storing the dictionary, finding the nearest four words to a given input word if it is not in the dictionary, and adding a new word to the dictionary.

# Time and Space Complexity

<p class="has-line-data" data-line-start="0" data-line-end="1"> The analysis for each operation, including the time and space complexity, and then the overall time complexity:</p>
<ol>
<li class="has-line-data" data-line-start="2" data-line-end="6">
<p class="has-line-data" data-line-start="2" data-line-end="3"><code>read_dictionary(file_path)</code>:</p>
<ul>
<li class="has-line-data" data-line-start="3" data-line-end="4">Time Complexity: O(n * log n), where n is the number of words in the file. The set comprehension creates a set of words with a time complexity of O(n), and sorting the set takes O(n * log n) time complexity.</li>
<li class="has-line-data" data-line-start="4" data-line-end="6">Space Complexity: O(n), where n is the number of words in the file. The set will store all unique words, and the returned sorted list will have the same number of elements.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="6" data-line-end="10">
<p class="has-line-data" data-line-start="6" data-line-end="7"><code>find_nearest_words(words_list, input_word)</code>:</p>
<ul>
<li class="has-line-data" data-line-start="7" data-line-end="8">Time Complexity: O(log n), where n is the number of words in the <code>words_list</code>. The <code>bisect.bisect_left</code> function performs a binary search, which has a time complexity of O(log n).</li>
<li class="has-line-data" data-line-start="8" data-line-end="10">Space Complexity: O(1). The variables <code>index</code>, <code>before</code>, and <code>after</code> have constant space requirements.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="10" data-line-end="14">
<p class="has-line-data" data-line-start="10" data-line-end="11"><code>SpellChecker.__init__(self, dictionary)</code>:</p>
<ul>
<li class="has-line-data" data-line-start="11" data-line-end="12">Time Complexity: O(1). Initializing the <code>SpellChecker</code> class with a given dictionary has a constant time complexity.</li>
<li class="has-line-data" data-line-start="12" data-line-end="14">Space Complexity: O(n), where n is the number of words in the dictionary. The <code>dictionary</code> attribute will store all the words.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="14" data-line-end="18">
<p class="has-line-data" data-line-start="14" data-line-end="15"><code>SpellChecker.is_word_in_dictionary(self, word)</code>:</p>
<ul>
<li class="has-line-data" data-line-start="15" data-line-end="16">Time Complexity: O(log n), where n is the number of words in the dictionary. The <code>in</code> operator in Python for lists uses a binary search, which has a time complexity of O(log n).</li>
<li class="has-line-data" data-line-start="16" data-line-end="18">Space Complexity: O(1). The method only uses a constant amount of space.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="18" data-line-end="22">
<p class="has-line-data" data-line-start="18" data-line-end="19"><code>SpellChecker.get_nearest_words(self, word)</code>:</p>
<ul>
<li class="has-line-data" data-line-start="19" data-line-end="20">Time Complexity: O(log n), where n is the number of words in the dictionary. The method uses the <code>find_nearest_words</code> function, which has a time complexity of O(log n).</li>
<li class="has-line-data" data-line-start="20" data-line-end="22">Space Complexity: O(1). The method only uses a constant amount of space.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="22" data-line-end="26">
<p class="has-line-data" data-line-start="22" data-line-end="23"><code>SpellChecker.add_word_to_dictionary(self, word)</code>:</p>
<ul>
<li class="has-line-data" data-line-start="23" data-line-end="24">Time Complexity: O(n), where n is the number of words in the dictionary. The <code>bisect.bisect_left</code> function performs a binary search to find the appropriate position, which has a time complexity of O(log n). However, the <code>insert</code> method of a list has a time complexity of O(n) in the worst case, as it needs to shift elements to make space for the new word.</li>
<li class="has-line-data" data-line-start="24" data-line-end="26">Space Complexity: O(1). The method only uses a constant amount of space.</li>
</ul>
</li>
<li class="has-line-data" data-line-start="26" data-line-end="30">
<p class="has-line-data" data-line-start="26" data-line-end="27">Main Part:</p>
<ul>
<li class="has-line-data" data-line-start="27" data-line-end="28">Time Complexity: The time complexity mainly depends on the user input and how many words are in the dictionary. The check for word validity and printing suggestions are generally constant time operations. However, the addition of a word to the dictionary depends on the <code>add_word_to_dictionary</code> method’s time complexity, which is O(n).</li>
<li class="has-line-data" data-line-start="28" data-line-end="30">Space Complexity: The space complexity mainly depends on the size of the dictionary loaded into memory.</li>
</ul>
</li>
</ol>

## Overall Time Complexity: 
<p class="has-line-data" data-line-start="30" data-line-end="31">The overall time complexity of the code is dominated by the time complexity of <code>read_dictionary</code>, which is O(n * log n), due to the sorting operation. The other operations in the code have lesser time complexities and do not significantly affect the overall time complexity. Therefore, the overall time complexity is O(n * log n).</p>

## Overall Space Complexity: 
<p class="has-line-data" data-line-start="32" data-line-end="33">The overall space complexity is O(n), where n is the total number of unique words present in the dictionary. This is because the dominant data structure in the code is the dictionary, which stores all the words read from the file and is of size O(n). Other variables and data structures used in the code have constant space requirements and do not contribute significantly to the overall space complexity.</p>

