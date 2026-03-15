Submission 2 from Group 16

This assignment has been made to fulfill the requirements for Parts 5a, 5b, and 5c plus the optional IfThenElse. 
We implemented the missing math operators and the PrintStatement across the different visitor classes.

For the WhileLoop and IfThenElse, since Mini Java doesn't have booleans, first we run a check if the evaluated integer expression is >= 0. 
If so, we execute the corresponding statements. You could also just add an actual boolean type to the language instead
of treating integers as booleans, but I am not sure how much more time that will take.

For the code coverage requirement, we added tests for all our new features to hit at least 90%. 
You will notice a few uncovered lines in the coverage report for ProgramTypeVisitor and ProgramExecutorVisitor 
(like throwing a RuntimeException if an operator function is null, or checking if a type is null). 
We could also have tried to write tests to hit them, but since those are just defensive checks for impossible states
that the type checker prevents anyway, we didn't think they were that relevant.

As for the overall flow of the program, first the program is serialized by the ProgramSerializerVisitor which formats the code. Then we sue the type visitor to check all the types are correct and we arent for example, adding a float and an int together. Then the program is executed with the programExecutorVisitor. Any problems that might be will be reported in the problems array.