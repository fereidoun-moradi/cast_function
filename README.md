# Cast_Function


![toolset3](https://user-images.githubusercontent.com/45528113/199219377-742ded4c-0063-4347-8961-4504f5b6f01e.jpg)




The <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfunction_variables">cast function</a> maps a state space genrated by Afra model checker to the state space of the mCRL2. 
It outputs the state space in <a href="https://www.mcrl2.org/web/user_manual/language_reference/lts.html#language-aut-lts">aut (Aldebaran) format</a>. The mapped state space can be used as the input file in mCRL2 tool for abstracting the transtion system based on <a href="https://www.mcrl2.org/web/user_manual/tools/release/ltsconvert.html">difference equivalence relationships</a> and a list of silent (tau) transtions.

The <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfunction_variables.lf">source code</a> of the cast function is developted in c++ and compiled by  <a href="https://www.lf-lang.org/download">Lingua Franca (LF)</a> compiler. 

The <a href="https://github.com/fereidoun-moradi/extraction_Function">extraction function</a> generates a list of labels for silent (tau) transtions. 
 

# Example 1: Temperature Control System (simplified version).
Input state space a <a href="https://github.com/fereidoun-moradi/Abstraction-tool/blob/main/RV-Example.rebeca">Timed Rebeca</a> model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/temp_graph_org.pdf">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/RV-Example.statespace">state space file</a>

The example is a reactive system and its diagram shows that it has recurrent behavior. Each state shows state variables 'temperature', which its value is changed when the action 'tempchange' is executed. The  'time + = 10' denotes that the logical time progresses by 10 units of time. Transitions show the enabled actions at the states and the progress of time. 
The shift equivalence relation exists between states (in blue color in the diagram) and the values of the time shifting are tagged on transitions. The label 'a>>b' indicates that the time value 'a' is shifted by the amount of 'b'.

List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list">ignore list</a>

LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile.aut">aut file</a> (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/temp_graph_LTS.pdf">LTS diagram</a>)

<img width="1152" alt="Screenshot 2023-03-03 at 09 22 10" src="https://user-images.githubusercontent.com/45528113/222669059-1e046e84-7076-4f96-bc9d-a5267f36619a.png">



# Example 2.
The diagram of the messages passing between actors defined in a <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/OneRoomTemp_mode.rebeca">Timed Rebeca</a>  model of a room temperature control system.

![diagram_actors_messages](https://user-images.githubusercontent.com/45528113/198962230-89231591-082f-4591-b449-b58471ea3488.jpg)

Input state space of a Timed Rebeca model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/state_transition_diagram.png">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/OneRoomTemp_mode.statespace">state space file</a> (The state space includes 76 states and 103 transtions)

List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list_exp2">ignore list</a>
(This variables list is selected among the variables whose values are changed by the observable actions, i.e., observable messages)

Mapped LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile_exp2.aut">aut file</a> (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/state%20transition%20diagram%20exp2.png">LTS diagram</a>) (the aut file contains 103 states and 129 transtions, and the dot file (LTS diagram) is generated using ltsconvert function in mCRL2 tool.)



Below is the console screen of the cast function.
![Screenshot 2022-10-31 at 09 52 04](https://user-images.githubusercontent.com/45528113/198969112-9cd46046-db00-4273-afe9-8d337abae538.png)



# Example 3.
The diagram of the messages passing between actors defined in a <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/SWaT_Time_WithoutAttacks.rebeca">Timed Rebeca</a> model of a secure water treatment system.

![diagram_actors_messages_swat drawio](https://user-images.githubusercontent.com/45528113/199199300-2946742b-285a-46f4-b825-2d81adfcd6ee.png)


Input state space of a Timed Rebeca model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/SWaT_Time_WithoutAttacks.pdf">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/SWaT_Time_WithoutAttacks.statespace">state space file</a> (The state space includes 688 states and 1825 transtions)

![Screenshot 2022-11-01 at 10 31 59](https://user-images.githubusercontent.com/45528113/199203830-1efc2b37-976d-4a3d-8807-baec7d2ff869.png)



List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list_exp3.txt">ignore list</a>
(This variables list is selected among the variables whose values are changed by the observable actions, i.e., observable messages. In this example, all variables except sensedTank1WaterLevel, sensedTank2WaterLevel, and sensedTank3WaterLevel )

Mapped LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile_exp3.aut">aut file</a> (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/SWaT_Time_WithoutAttacks_casted_v2_dot.pdf">LTS diagram</a>) (the aut file contains 760 states and 1896 transtions, and the dot file (LTS diagram) is generated using ltsconvert function in mCRL2 tool.)

