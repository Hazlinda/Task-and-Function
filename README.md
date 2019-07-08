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
   
