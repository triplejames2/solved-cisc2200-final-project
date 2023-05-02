Download Link: https://assignmentchef.com/product/solved-cisc2200-final-project
<br>



In this project, you will implement a calculator which could do calculation.

The input of this calculator should be in the format of infix notation:

(6 + 13) * 2 – (5 + 1)/3

To evaluate an infix expression, the calculator first converts the expression to postfix notation, and then evaluate it.  The format of postfix notation of the above input is:

6 13  +  2 * 5  1  + 3  /  –

Only four arithmetic operations are allowed in an expression:  +, -, *, /.

The program should read the infix input from the standard input, print the expression in the postfix format on the screen, and then print the evaluated value of the expression.

You should check errors of the input string in case it is not syntactically and semantically correct. In other words, there may be input such as “1+2*”, “(1+2))” or “1/0”. You should create your own Exception classes to handle these errors.

Algorithm to convert from infix to postfix (with a stack)

<ol>

 <li>Examine the next element in the input.</li>

 <li>If it is an operand, output it.</li>

 <li>If it is opening parenthesis, push it on stack.</li>

 <li>If it is an operator, then

  <ol>

   <li>If stack is empty, push operator on stack.</li>

   <li>If the top of the stack is opening parenthesis, push operator on stack.</li>

   <li>If it has higher priority than the top of stack, push operator on stack.</li>

   <li>Else pop the operator from the stack and output it, repeat step 4.</li>

  </ol></li>

 <li>If it is a closing parenthesis, pop operators from the stack and output them until an opening parenthesis is encountered. Pop and discard the opening parenthesis.</li>

 <li>If there is more input go to step 1</li>

 <li>If there is no more input, unstack the remaining operators to output.</li>

</ol>

Algorithm to evaluate postfix expression (with a stack)

<ol>

 <li>Scan the given postfix expression from left to right</li>

 <li>for each token in the input postfix expression

  <ol>

   <li>if the token is an operand

    <ol>

     <li>push it (its value) onto a stack</li>

    </ol></li>

   <li>else if the token is an operator

    <ol>

     <li>get operand2 by popping up the stack ii. get operand1 by popping up the stack</li>

    </ol></li>

  </ol></li>

</ol>

<ul>

 <li>compute operand1 operator operand2</li>

</ul>

<ol start="3">

 <li>push result onto the stack</li>

 <li>return top of the stack as result</li>

</ol>

Please use Stack template class from C++ STL to finish this project.




Submit: finalProject.cpp and any other class files.