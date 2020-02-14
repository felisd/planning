## PDDL3 solver for temporal and non-temporal planning problems

### How to compile

```
cd ./tempo-sat-sgplan6
make
```

### How to run

After compiling, run `sgplan` in the `tempo-sat-sgplan6` directory.

Usage :

`./sgplan -o [domain_file] -f [problem_file] -out [solution_file] -cputime [max_cpu_time_in_seconds]`

Example:

`./sgplan -o ../demo-domain/domain.pddl -f ../demo-domain/prob01.pddl -out p01.soln -cputime 20`

### Original README

15-887 course project by Carlo Angiuli, Ben Blum, and Michael Sullivan.

Stuff here:

report/ - source for the report

tempo-sat-sgplan6/ - the source for the planner we used, modified to build.

concurrency-domain/ - the domain and problem files for our assembly like
                      shared memory concurrency domain
 - threads.pddl is the domain file
 - the rest are various tests

demo-domain/ - a demo domain with very simple operations on natural numbers

lambda-domain/ - two failed attempts to implement the lambda calculus
 - lambda.pddl - a domain for a partially implemented substitution based
                 lambda calculus evaluator
 - lambda-ctx.pddl - a domain for a fully implemented environment passing
                     based lambda calculus evaluator
 - some tests

plus-domain/ - an implementation of Prolog-style natural number addition
 - plus.pddl - the plus domain
 - some tests

ski-domain/ - an attempt to embed the SKI combinator calculus
 - SKI.hs - a SKI evaluator in haskell
 - ski.pddl - the SKI domain
 - some tests

threads-cmplr/ - a compiler for a simple imperative language to the
                 threads domain
 - parser/ - the parser code - some of it cribbed from the base code
                 for an assignment given out when mjsulliv@ was a
                 15-312 TA
 - language.sml - the AST of the frontend language
 - compile.sml - intermediate languages and translations between them;
                 the code for converting a label based assembly
                 language to an address based one modified from code
                 mjsulliv@ wrote for a project once
 - output.sml - pretty printer
 - top.sml - top level that pulls the pieces together

 - run.sml - script to run the compiler to generate all of the output
   files we want. Running 'sml run.sml' from a shell in the
   threads-cmplr directory should generate all the generated domain
   files.
