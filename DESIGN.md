# Design

Since the inital idea to build klo a lot of time has passed. In the beginning
I just wanted to rewrite the neo optimizer to have better performance, but
since then my idea of klo changed. To better explain what this project wants to
achieve and how it is doing it I started writing this document.

## One Thing Well

I always liked the unix philosophy of doing one thing well and piping things
around - and evertime I use a tool that does not support that workflow I am a
little bit sad. And this is what happened with the optimizer from arne too. 
While the application uses modules a lot of times they are not designed to be
used standalone.

## Taking The Keyboard Layout Optimizing Process Apart

The way I look at it the project needs to do the following things well:

0) Common Data Structure
0) Build Ngramm scores (without hard coded settings) from different sources
0) Compare layouts using ngramm scores
0) Create new random layouts
0) Evolve layouts to get a better score
0) A tool to automate everything

## Common Rules

For each of the resulting applications the following rules should be fullfilled:

- XDG config files
- output to stdout or file as plain text or json
- input from stdin or files
- command line arguments to override config options
- use multithreading
- allow long running processes to be paused & continued
