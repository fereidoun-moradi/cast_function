# Cast_Function

The <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfunction_variables">function</a> mapps a state space genrated by Afra model checker to a Labeled Trantion System (LTS). 
It gets a list of variables while couples values of the state variables from states to the transtion labels. 
It outputs a LTS in <a href="https://www.mcrl2.org/web/user_manual/language_reference/lts.html#language-aut-lts">aut (Aldebaran) format</a>. The created LTS can be used as the input file in mCRL2 tool for reducing the transtion system based on <a href="https://www.mcrl2.org/web/user_manual/tools/release/ltsconvert.html">difference equivalence relationships</a> and tau transtions.

The <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfunction_variables.lf">source code</a> of the function is developted in c++ and compiled by  <a href="https://www.lf-lang.org/download">Lingua Franca (LF)</a> compiler. 



# Example 1.
Input state space of a <a href="https://github.com/fereidoun-moradi/Abstraction-tool/blob/main/RV-Example.rebeca">Timed Rebeca</a> model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/RV_Example.png">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/RV-Example.statespace">state space file</a>

List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list">ignore list</a>

Mapped LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile.aut">aut file</a> (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/mapped_lts.pdf">LTS diagram</a>)

![Screenshot 2022-07-05 at 12 04 32](https://user-images.githubusercontent.com/45528113/177304089-46e46617-750b-4b88-a831-032044330d7b.png)

# Example 2.
The diagram of the messages passing between actors defined in a model of a room temperature control system.

![diagram_actors_messages](https://user-images.githubusercontent.com/45528113/198962230-89231591-082f-4591-b449-b58471ea3488.jpg)

Input state space of a <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/OneRoomTemp_mode.rebeca">Timed Rebeca</a> model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/state_transition_diagram.png">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/OneRoomTemp_mode.statespace">state space file</a> (it includes 76 states and 103 transtions)
