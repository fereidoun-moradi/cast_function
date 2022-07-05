# Cast_Function

The <a href="https://github.com/fereidoun-moradi/Abstraction-tool/blob/main/input.txt">function</a> mapps a state space genrated by Afra model checker to a Labeled Trantion System (LTS). 
It gets a list of variables while couples values of the state variables from states to the transtion labels. 
It outputs a LTS in <a href="https://www.mcrl2.org/web/user_manual/language_reference/lts.html#language-aut-lts">aut (Aldebaran) format</a>. The created LTS can be used as the input file in mCRL2 tool for reducing the transtion system based on <a href="
https://www.mcrl2.org/web/user_manual/tools/release/ltsconvert.html">difference equivalence relationships</a> and tau transtions.

# Example.
Input state space of a <a href="https://github.com/fereidoun-moradi/Abstraction-tool/blob/main/RV-Example.rebeca">Timed Rebeca</a> model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/RV_Example.png">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/RV-Example.statespace">state space file</a>

List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list">variables list</a>

Mapped LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile.aut">aut file</a>



