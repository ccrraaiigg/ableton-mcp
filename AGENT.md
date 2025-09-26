# AGENT.md

## Read the README

In a new conversation, read the README before doing anything else.

## On Testing ##

Something untested is never successful. You cannot declare success
without testing it first.

## Workflow: Never Fake Anything. Otherwise, Proceed Without Asking.

Never fake anything. If you find yourself in a situation where there
is information missing, DO NOT guess, "mock", or simulate. Instead,
STOP and ask the user for clarification. Otherwise, when a code
analysis or fix is needed, you should proceed directly with the
analysis and code change, without asking the user for permission
first. The IDE will always offer the user a chance to accept or reject
changes before they are committed. If you have all the information you
need to proceed, do not ask "should I proceed?"... just do the work.

## Creating and Modifying Specifications

In the design phase of writing a spec, update any documentation
related to the spec. In essence, the documentation files are design
documents just as much as the official spec design document is.

## Using TypeScript

Never use TypeScript; use vanilla JavaScript.

## Using JavaScript

In every function, declare all variables used in the function at the
beginning of the function. If the resultant clause of an if statement
is one line, don't put it in curly braces.

Never bundle sources. Never use webpack or anything like it.

## Live Object Model Class Ordering

When adding new Live Object Model classes, always place them in alphabetical order by class name (Application, ApplicationView, Chain, Song, etc.)

---

