# Overview
Control flow statements are used to run pieces of code that are dependent on the situation.   

* Example 1: You want to run a different autonomous mode depending on your starting location
* Example 2: You want to stop the robot elevator from rising past a certain point

To do this, you will need to add logic.
For FRC, you will typically only need if-then-else statements.

###### Operators

Operator | Meaning | 
:----------- |:-------------| 
&&         	| AND       					 | 
||         	| OR       						 | 
==			| Equal to     				  	 | 
>=			| Greater than or equal to       | 
<=			| Less than or equal to      	 | 


###### If-Then-Else
```
if (CONDITION1) {	
	CODE_BLOCK_1	 
} else {
	CODE_BLOCK_2
}
```
If CONDITION1 is `true`, then the code between `{` and `}` is run (`CODE_BLOCK_1`).   
If `false`, the code between `{` and `}` after the else is run (`CODE_BLOCK_2`).

###### Example
```
	if (testscore >= 90) {
		grade = 'A';
	} else if (testscore >= 80) {
		grade = 'B';
	} else if (testscore >= 70) {
		grade = 'C';
	} else if (testscore >= 60) {
		grade = 'D';
	} else {
		grade = 'F';
	}
```