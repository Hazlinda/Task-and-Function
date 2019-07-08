# Task-and-Function

Supporting system for systemverilog are tasks and functions.
Tasks and functions are both subroutines. That allows you to abstract the repeated code of any program.
System Verilog makes a number of extensions to basic verilog syntax.

# Tasks

        task automation my_task(input int local_a, int local_b);
          if(local_a == local_b)
            begin
              my_task(local_a == local_b);
              return; //end 'this' copy of task
            end
            
              global_a = local_a;
              blobal_b = local_b;
        endtask
            
   Explaination about coding above:
   task automatic - automatic tasks allocate memory dynamically at call time.
   input - default port direction is input
   int local_a and int local_b - ANSI style port list, type, even struct etc
   return - return keyword in supported and terminates task at that point
   
# Function

Function we also looks like with tasks.

Example:

        function automatic int factorial (int n);
              if (n==0) return(1);    //factorial for '0' is '1'
              else return (factorial (n-1)*n);
        endfunction
            
  Explaination about coding above:
  automatic - automatic function allocate memory dynamically at call time (fulll recursion)
  int - Default port direction is input (also support output)
  n - ANSI style portlist also arguments and return type can be any SV-type, even complex structs, etc.
  return - return (value) is supported and terminas function at that point
  
A function which does not return any value is a void fuction

Example:

        function void interval ();      //interval means return type of void means no return value
           a=!a
        endfunction
           reg a;
        initial
           interval();   
      
        
Function called like a task. Recomended style (instead of writing a task) to guarantee a task execute with '0' delay.
        
  # Task and Function Usage
  
 Task
 
 Task can enable other tasks and functions
 Task may execute in non-zero simulation time
 task may have zero or more arguments of type input, output and inout
 
 Function
 
 Function can enable other function only. Task can not be called from functions
 Function should
