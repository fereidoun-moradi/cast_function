# Cast_Function


![toolset3](https://user-images.githubusercontent.com/45528113/199219377-742ded4c-0063-4347-8961-4504f5b6f01e.jpg)




The <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfunction_variables">function</a> mapps a state space genrated by Afra model checker to a Labeled Trantion System (LTS). 
It outputs a LTS in <a href="https://www.mcrl2.org/web/user_manual/language_reference/lts.html#language-aut-lts">aut (Aldebaran) format</a>. The created LTS can be used as the input file in mCRL2 tool for reducing the transtion system based on <a href="https://www.mcrl2.org/web/user_manual/tools/release/ltsconvert.html">difference equivalence relationships</a> and tau transtions.

The <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfunction_variables.lf">source code</a> of the function is developted in c++ and compiled by  <a href="https://www.lf-lang.org/download">Lingua Franca (LF)</a> compiler. 

Note: The cast function has an option that can get a list of variables as an input list (ignore list) and put the variable's values which are not in the list on the transtions of the mapped state space. To ignore all variables, the ignore list must include all variables name exist in the state space model. 

# Example 1.
Input state space of a <a href="https://github.com/fereidoun-moradi/Abstraction-tool/blob/main/RV-Example.rebeca">Timed Rebeca</a> model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/RV_Example.png">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/RV-Example.statespace">state space file</a>

List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list">ignore list</a>

Mapped LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile.aut">aut file</a> (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/mapped_lts.pdf">LTS diagram</a>)

![Screenshot 2022-07-05 at 12 04 32](https://user-images.githubusercontent.com/45528113/177304089-46e46617-750b-4b88-a831-032044330d7b.png)

# Example 2.
The diagram of the messages passing between actors defined in a model of a room temperature control system.

![diagram_actors_messages](https://user-images.githubusercontent.com/45528113/198962230-89231591-082f-4591-b449-b58471ea3488.jpg)

Input state space of a <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/OneRoomTemp_mode.rebeca">Timed Rebeca</a> model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/state_transition_diagram.png">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/OneRoomTemp_mode.statespace">state space file</a> (The state space includes 76 states and 103 transtions)

List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list_exp2">ignore list</a>
(This variables list is selected among the variables whose values are changed by the observable actions, i.e., observable messages)

Mapped LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile_exp2.aut">aut file</a> (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/state%20transition%20diagram%20exp2.png">LTS diagram</a>) (the aut file contains 103 states and 129 transtions, and the dot file (LTS diagram) is generated using ltsconvert function in mCRL2 tool.)



Below is the console screen of the cast function.
![Screenshot 2022-10-31 at 09 52 04](https://user-images.githubusercontent.com/45528113/198969112-9cd46046-db00-4273-afe9-8d337abae538.png)



# Example 3.
The diagram of the messages passing between actors defined in a model of a secure water treatment system.

![diagram_actors_messages_swat drawio](https://user-images.githubusercontent.com/45528113/199199300-2946742b-285a-46f4-b825-2d81adfcd6ee.png)


Input state space of a <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/SWaT_Time_WithoutAttacks.rebeca">Timed Rebeca</a> model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/SWaT_Time_WithoutAttacks.pdf">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/SWaT_Time_WithoutAttacks.statespace">state space file</a> (The state space includes 688 states and 1825 transtions)

![Screenshot 2022-11-01 at 10 31 59](https://user-images.githubusercontent.com/45528113/199203830-1efc2b37-976d-4a3d-8807-baec7d2ff869.png)



List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list_exp3.txt">ignore list</a>
(This variables list is selected among the variables whose values are changed by the observable actions, i.e., observable messages. In this example, all variables except sensedTank1WaterLevel, sensedTank2WaterLevel, and sensedTank3WaterLevel )

Mapped LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile_exp3.aut">aut file</a> (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/SWaT_Time_WithoutAttacks_casted_v2_dot.pdf">LTS diagram</a>) (the aut file contains 760 states and 1896 transtions, and the dot file (LTS diagram) is generated using ltsconvert function in mCRL2 tool.)

