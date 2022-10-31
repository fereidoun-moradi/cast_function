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

Input state space of a <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/OneRoomTemp_mode.rebeca">Timed Rebeca</a> model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/state_transition_diagram.png">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/OneRoomTemp_mode.statespace">state space file</a> (The state space includes 76 states and 103 transtions)

List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list_exp2">ignore list</a>
(This variables list is selected among the variables whose values are changed by the observable actions, i.e., observable messages)

Mapped LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile_exp2.aut">aut file</a> (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/state%20transition%20diagram%20exp2.png">LTS diagram</a>) (It contains 103 states and 129 transtions)


Below is the console screen of the cast function.

Last login: Fri Oct 21 09:49:05 on console
/Users/fmi04/runtime-EclipseXtext/roomT_GitHub/src-gen/bin/castfunction_variables ; exit;
C02Y60HEJHD4:~ fmi04$ /Users/fmi04/runtime-EclipseXtext/roomT_GitHub/src-gen/bin/castfunction_variables ; exit;
[INFO]  Starting the execution
Loading a state transition system (LTS)!
Please enter your file name (*.statespace) with directory path (e.g., /Users/fmi04/src-gen/bin/RV-Example.statespace): 
/Users/fmi04/runtime-EclipseXtext/roomT_GitHub/src-gen/bin/OneRoomTemp_mode.statespace 
Please enter yes(Y) or no(N): 
Is LTS be annotated with variable values on transitions? 
Y
Please write ignore list of variables: (no list: (N) or variable names separated with comma)? 
temperature,air_blowing,heating,cooling,heater_on,cooler_on
NUBMER OF STATES: 103 NUBMER OF TRANSITIONS: 129
(0,"start_[22_]",1)
(1,"status_[22_]",2)
(1,"status_[22_]",3)
(1,"status_[22_]",4)
(2,"sense_[22_]",5)
(3,"sense_[22_]",7)
(4,"sense_[22_]",9)
(5,"time +=10",6)
(6,"getsense_[21_]",11)
(7,"time +=10",8)
(8,"getsense_[22_]",12)
(9,"time +=10",10)
(10,"getsense_[23_]",13)
(11,"start_[21_]",14)
(12,"start_[22_]",76)
(13,"start_[23_]",15)
(14,"status_[21_]",16)
(14,"status_[21_]",17)
(14,"status_[21_]",18)
(15,"status_[23_]",19)
(15,"status_[23_]",20)
(15,"status_[23_]",21)
(16,"sense_[21_]",22)
(17,"sense_[21_]",32)
(18,"sense_[21_]",24)
(19,"sense_[23_]",26)
(20,"sense_[23_]",30)
(21,"sense_[23_]",28)
(22,"time +=10",23)
(23,"getsense_[20_]",34)
(24,"time +=10",25)
(25,"getsense_[22_]",46)
(26,"time +=10",27)
(27,"getsense_[22_]",35)
(28,"time +=10",29)
(29,"getsense_[24_]",47)
(30,"time +=10",31)
(31,"getsense_[23_]",36)
(32,"time +=10",33)
(33,"getsense_[21_]",37)
(34,"activate_h_[20_]",38)
(35,"start_[22_]",39)
(36,"start_[23_]",40)
(37,"start_[21_]",41)
(38,"heating_[20_]",42)
(39,"status_[22_]",77)
(39,"status_[22_]",78)
(39,"status_[22_]",79)
(40,"status_[23_]",80)
(40,"status_[23_]",81)
(40,"status_[23_]",82)
(41,"status_[21_]",83)
(41,"status_[21_]",84)
(41,"status_[21_]",85)
(42,"status_[20_]",43)
(42,"status_[20_]",44)
(42,"status_[20_]",45)
(43,"sense_[20_]",55)
(44,"sense_[20_]",48)
(45,"sense_[20_]",50)
(46,"start_[22_]",52)
(47,"activate_c_[24_]",53)
(48,"time +=10",49)
(49,"getsense_[21_]",72)
(50,"time +=10",51)
(51,"getsense_[22_]",67)
(52,"status_[22_]",86)
(52,"status_[22_]",87)
(52,"status_[22_]",88)
(53,"cooling_[24_]",54)
(54,"status_[24_]",57)
(54,"status_[24_]",58)
(54,"status_[24_]",59)
(55,"time +=10",56)
(56,"getsense_[20_]",66)
(57,"sense_[24_]",60)
(58,"sense_[24_]",62)
(59,"sense_[24_]",64)
(60,"time +=10",61)
(61,"getsense_[22_]",74)
(62,"time +=10",63)
(63,"getsense_[23_]",68)
(64,"time +=10",65)
(65,"getsense_[24_]",69)
(66,"resume_heating_[20_]",89)
(67,"switchoff_[22_]",70)
(68,"switchoff_[23_]",71)
(69,"resume_cooling_[24_]",90)
(70,"status_[22_]",91)
(70,"status_[22_]",92)
(70,"status_[22_]",93)
(71,"status_[23_]",94)
(71,"status_[23_]",95)
(71,"status_[23_]",96)
(72,"switchoff_[21_]",73)
(73,"status_[21_]",97)
(73,"status_[21_]",98)
(73,"status_[21_]",99)
(74,"switchoff_[22_]",75)
(75,"status_[22_]",100)
(75,"status_[22_]",101)
(75,"status_[22_]",102)
(76,"@(10>>10)",1)
(77,"@(20>>20)",2)
(78,"@(20>>20)",3)
(79,"@(20>>20)",4)
(80,"@(20>>10)",19)
(81,"@(20>>10)",20)
(82,"@(20>>10)",21)
(83,"@(20>>10)",16)
(84,"@(20>>10)",17)
(85,"@(20>>10)",18)
(86,"@(20>>20)",2)
(87,"@(20>>20)",3)
(88,"@(20>>20)",4)
(89,"@(30>>10)",38)
(90,"@(30>>10)",53)
(91,"@(30>>30)",2)
(92,"@(30>>30)",3)
(93,"@(30>>30)",4)
(94,"@(30>>20)",19)
(95,"@(30>>20)",20)
(96,"@(30>>20)",21)
(97,"@(30>>20)",16)
(98,"@(30>>20)",17)
(99,"@(30>>20)",18)
(100,"@(30>>30)",2)
(101,"@(30>>30)",3)
(102,"@(30>>30)",4)
[INFO]  Terminating the execution
logout
Saving session...
...copying shared history...
...saving history...truncating history files...
...completed.
Deleting expired sessions...84 completed.

[Process completed]




