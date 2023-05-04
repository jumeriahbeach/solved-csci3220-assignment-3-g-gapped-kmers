Download Link: https://assignmentchef.com/product/solved-csci3220-assignment-3-g-gapped-kmers
<br>
In this assignment, you will use different ways to compute sequence similarity based on <em>g</em>-gapped <em>k</em>mers, to experience their relative. You will then perform some probability derivations using the three basic rules, and solve some generic problems. Finally, you will implement the forward algorithm for computing data likelihoods according to a first-order hidden Markov model, in a way that your program can handle any type of sequences.

<ol>

 <li>This question is about <em>g</em>-gapped <em>k</em>-mers. Suppose we want to compute a similarity score between DNA sequences <em>s</em><sub>1</sub>=GCGTCCGAC and <em>s</em><sub>2</sub>=CGACGCGAC based on 1-gapped 3-mers (i.e., <em>g</em>=1, <em>k</em>=3).</li>

</ol>

<ul>

 <li>How many different 1-gapped 3-mer patterns are there for DNA sequences? Show the steps in your calculation.</li>

 <li>List all the 1-gapped 3-mers actually supported by <em>s</em><sub>1</sub> and <em>s</em><sub>2</sub> and their occurrence counts in the two sequences by filling in the following tables (add more rows if needed). The tables should be sorted in ascending order of the 1-gapped 3-mers, where the wildcard character * is ordered before the four nucleotides. Table for <em>s</em><sub>1         </sub>Table for <em>s</em><sub>2 </sub></li>

</ul>

<table width="0">

 <tbody>

  <tr>

   <td width="143">1-gapped 3-mer</td>

   <td width="144">No. of occurrence</td>

   <td rowspan="2" width="15"> </td>

   <td width="143">1-gapped 3-mer</td>

   <td width="144">No. of occurrence</td>

  </tr>

  <tr>

   <td width="143"> </td>

   <td width="144"> </td>

   <td width="143"> </td>

   <td width="144"> </td>

  </tr>

 </tbody>

</table>







<ul>

 <li>Based on your tables in Part b, compute the similarity between the two sequences, defined as the inner product of the two 1-gap 3-mer occurrence vectors. Show clearly the common</li>

</ul>

1-gap 3-mers of the two sequences in your calculations.




<ul>

 <li>Now complete the following table listing the number of mismatches among the 4-mers in the two sequences. The row and column headers should be the 4-mers present in <em>s</em><sub>1</sub> and <em>s</em><sub>2</sub>, respectively, both sorted ascendingly. If a 4-mer appears multiple times in a sequence, repeat it that number of times in the row/column headers.</li>

 <li>Based on your result in Part d, compute the similarity score between <em>s</em><sub>1</sub> and <em>s</em><sub>2</sub> Show the steps in your calculation. Do not forget to compare with your result in Part c.</li>

 <li>In practice, it is not easy to decide which values of <em>g</em> and <em>k</em> to use. One possible approach is to try multiple combinations of these values, and use some independent knowledge to evaluate which combination leads to the best similarity scores. Propose two ideas for reducing the total computational time as compared to repeating the above calculations for each combination of <em>g</em> and <em>k</em></li>

</ul>

<ol start="2">

 <li>This question is about statistical modeling. Suppose <em>Y</em> is a binary variable, and we want to construct a model of <em>Y</em> based on binary features <em>X</em><sub>1</sub> and <em>X</em><sub>2</sub>, which may not be conditionally independent.</li>

</ol>

<ul>

 <li>Derive a formula for computing Pr(<em>Y</em>=0|<em>X</em><sub>1</sub>=1,<em>X</em><sub>2</sub>=1) in terms of Pr(<em>X</em><sub>1</sub>=1), Pr(<em>X</em><sub>1</sub>=1,<em>X</em><sub>2</sub>=0) and Pr(<em>X</em><sub>1</sub>=1,<em>X</em><sub>2</sub>=1,<em>Y</em>=1). Show your derivations step by step.</li>

 <li>[Optional] In general, with three variables <em>X</em><sub>1</sub>, <em>X</em><sub>2</sub> and <em>Y</em>, there are various possible probabilities of the form Pr(V<sub>L</sub>=v<sub>l</sub>|V<sub>R</sub>=v<sub>r</sub>), where V<sub>L</sub> and V<sub>R</sub> are two disjoint ordered sets of variables (and V<sub>R</sub> can be empty), and v<sub>l</sub> and v<sub>r</sub> are their corresponding values. For example, in the case of Pr(<em>X</em><sub>1</sub>=1), V<sub>L</sub>=(<em>X</em><sub>1</sub>), v<sub>l</sub>=(1), and V<sub>R</sub>= Æ. In the case of Pr(<em>Y</em>=0|<em>X</em><sub>1</sub>=1,<em>X</em><sub>2</sub>=1), V<sub>L</sub>=(<em>Y</em>), v<sub>l</sub>=(0), V<sub>R</sub>=(<em>X</em><sub>1</sub>,<em>X</em><sub>2</sub>), and v<sub>r</sub>=(1,1).</li>

</ul>




Propose an algorithm that can take one of these probabilities as target (such as Pr(<em>Y</em>=0|<em>X</em><sub>1</sub>=1,<em>X</em><sub>2</sub>=1)) and some of these probabilities as input (such as Pr(<em>X</em><sub>1</sub>=1), Pr(<em>X</em><sub>1</sub>=1,<em>X</em><sub>2</sub>=0) and Pr(<em>X</em><sub>1</sub>=1,<em>X</em><sub>2</sub>=1,<em>Y</em>=1)), and determine whether the input is sufficient for inferring the value of the target.

<ul>

 <li>Now assume <em>X</em><sub>1</sub> and <em>X</em><sub>2</sub> are independent when conditioned on <em>Y</em>. Give a formal definition of this assumption using mathematical symbols.</li>

 <li>Depending on the values of <em>X</em><sub>1</sub>, <em>X</em><sub>2</sub> and <em>Y</em>, there are 8 probabilities of the form Pr(<em>X</em><sub>1</sub>,<em>X</em><sub>2</sub>|<em>Y</em>). Given an example set of values for these 8 probabilities such that <em>X</em><sub>1</sub> and <em>X</em><sub>2</sub> are not independent when conditioned on <em>Y</em>. Prove that the two variables are not conditionally independent</li>

 <li>If two variables <em>X</em><sub>1</sub> and <em>X</em><sub>2</sub> are independent when conditioned on <em>Y</em>, is it guaranteed that they are also unconditionally independent? Explain why or why not.</li>

 <li>If two variables <em>X</em><sub>1</sub> and <em>X</em><sub>2</sub> are unconditionally independent, is it guaranteed that they are also independent when conditioned on <em>Y</em>? Explain why or why not.</li>

</ul>

<ol start="3">

 <li>Write a computer program called <strong>Forward</strong> in C, C++, Java or Python that implements the forward algorithm to compute the data likelihood of a given sequence based on a first-order hidden Markov model. This program should be able to handle any number of states and any number of emission symbols. Your program should take the following inputs in the specified order, each on a different line: The number of states (an integer)

  <ul>

   <li>The initial probabilities of the states (floating-point numbers, one per line), in the order of p<sub>1</sub>, p<sub>2</sub>, …</li>

   <li>The transition probabilities among the states (floating-point numbers, one per line), in the order of <em>p</em><sub>11</sub>, <em>p</em><sub>12</sub>, …, <em>p</em><sub>21</sub>, <em>p</em><sub>22</sub>, …</li>

   <li>The number of emission symbols (an integer)</li>

   <li>The emission symbols (characters, one per line), in the order of <em>b</em><sub>1</sub>, <em>b</em><sub>2</sub>, …</li>

   <li>The emission probabilities (floating-point numbers, one per line), in the order of <em>e</em><sub>1</sub>(<em>b</em><sub>1</sub>), <em>e</em><sub>1</sub>(<em>b</em><sub>2</sub>), …, <em>e</em><sub>2</sub>(<em>b</em><sub>1</sub>), <em>e</em><sub>2</sub>(<em>b</em><sub>2</sub>), …</li>

   <li>The sequence the likelihood of which is to be computed (a string)</li>

  </ul></li>

</ol>




You can assume the input data are properly formatted and do not need to check for errors.

The output should be a single floating-point number of the likelihood value. Due to the inexact nature of floating-point numbers, when we check your answers a small amount of leeway may be considered.

The non-comment portion of your program is expected to contain no more than 200 lines of code.

Here is an expected screen shot when a Java program is run on an example from the lecture notes:

<table width="0">

 <tbody>

  <tr>

   <td width="629">&gt;java Forward20.50.50.90.10.80.24ACGT0.50.5 000.250.75 00CAC0.15156250000000002</td>

  </tr>

 </tbody>

</table>











