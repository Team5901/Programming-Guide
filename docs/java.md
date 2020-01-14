# Overview
The programing language Team 5901 uses is Java.    
The goal is to provide students basic Java knowledge to survive build season.     

**This is NOT a comprehensive guide on Java - refer to online guides for a more detailed guide,**      

## Commenting code

COmments can be used to document code, but can also be used to ignore parts of code.     
Single-line comments start with two forward slashes (//).     
Multi-line comments start with /* and ends with */.

```
// This is a comment
System.out.println("Hello World");
```

Any text between /* and */ will be ignored by Java.
  
## Variables & Data Types
In Java, variables store data values.     
Different data values are represented by different **Data Types**.       
Data types represent different kinds of variables.      
Some variables store numbers, other stores text, etc.    

To create a variable, the following syntax is used:     

```
<type> <variable name> = <value>;
```
  

A few of the common ones we will use can be seen below:

Data Type | Description | Example Declaration
----------|--------------|-------
int		| stores integers  | int age = 5;
double | stores fractional numbers| double cost = 3.5;
boolean | stores true or false| boolean LightOn = true;
String | Stores text, surrounded by double quotes| String Name = "Cougar Pack";


## Math Functions

Sometimes, our algorithm will require us to make calculations.     
Here are some common functionss we may use:     

Function| Description | Example Usage
--------|-------------|---------------
Math.max(x,y)| returns the maximum of x and y | Math.max(20,5) would be return as 20
Math.min(x,y)| returns the minimum of x and y | Math.min(20,5) would be return as 5
Math.sqrt(x)| returns the square root of x | Math.sqrrt(100) would be return as 10 
Math.abs(x)| reutnrs absolute value of x | Math.abs(-100) would return 100     


## Operators

Operators perform operations on variables and values.    
Here are some common operators we may use:    


### Arithmetic Operators

Operator | Description | Example Usage
---------|-------------|-------------
+ | addition | 5+3 returns 8
- | subtraction | 5 - 3 returns 2
* | multiplication |  5* 3 returns 15
/ | division | 5/3 returns 1.66 
% | modulous (remainder) | 5%3 returns 2

### Comparison Operators

Comparison operators compare two values. The result is returned as a boolean (true or false)

Operator | Description | Example Usage
---------|-------------|-------------
== | Equal to |  5 == 3 would return false
!= | Not Equal | 5 != 3 would return true
> | Greater than | 5 > 3 would return true. 5 > 5 would return false.
< | Less than | 5 < 3 would return false. 5 < 3 would return false.
>= | Greater than or equal to | 5 >= 3 would return true. 5 >= 5 would return true.
<= | Less than or equal to | 5 < 3 would return false. 5 <= 5 would return true.

### Comparison Operators

Logical operators are used to determine logic between variables

Operator | Description | Example Usage
---------|-------------|-------------
&& | AND - returns true if both statements are true | (5 > 3) && (6 > 6) would return false
&|&|| OR - returns true if either statement is true | (5 > 3) || (6 > 6) would return true
! | NOT - returns true if false, return false if true | !(5 > 3) would return false

## If-else

If-elses are used for control logic

```
if (condition1) {

}
else if (condition2) {

}
else {


}
```

Example:
```
int grade = 75;

if (grade > 90){     
	system.out.println("Grade is an A");
}
else if (grade > 80){
	system.out.println("Grade is an B");
}
else if (grade > 70){
	system.out.println("Grade is an C");
}
else if (grade > 60){
	system.out.println("Grade is an D");
}
else {
	system.out.println("Grade is an F");
}
```

## Methods

A method is a block of code which only runs when it is called.     
Arugments can be passed into methods, similiarly to a math function such as f(x) =  5x, where different values of x can be passed for different answers.     
This allows methods to be **reused** - you dont need seperate lines of code for controlling different motor speeds!

    

**Syntax**
```
public <return type> <method name>(datatype argument){

}
```


In the following example, the method below can be used to make a robot drive forward, drive backwards, OR stop completely!

**Example**
```
public void elevatorMove(double power){
	elevatorMotor(power);
	System.out.println("Running elevator at" + power;
}
```

Later, this method can be called in multiple ways to have different functions:

```
arcadeDrive(1.0) // robot drives forward
arcadeDrive (0.0) // robot stops
arcadeDrive(-1.0) // robot drives backwards
```


This is equivalent to running the following:

```
elevatorMotorPower(1.0);
System.out.println("Running elevator at" + 1.0);
elevatorMotor(0.0);
System.out.println("Running elevator at" + 0.0);
elevatorMotor(-1.0);
System.out.println("Running elevator at" + -1.0);
```



