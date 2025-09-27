# AGENT.md

## Read the README

In a new conversation, read the README before doing anything else.

## On Testing ##

Something untested is never successful. You cannot declare success
without testing it first.

## Workflow: Never Fake Anything. Otherwise, Proceed Without Asking.

Never fake anything. If you find yourself in a situation where there
is information missing, DO NOT guess, or "mock", or simulate. Instead,
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

Never use TypeScript; use vanilla JavaScript instead.

## Using JavaScript

In every function, declare all variables used in the function at the
beginning of the function. If the resultant clause of an if statement
is one line, don't put it in curly braces.

Never bundle sources. Never use webpack or anything like it.

## Editing tools JSON files

When editing the tools JSON files:

- The tools for a class should be in this order:
  - children getters
  - properties getters, then setters
  - functions
  
- Children getter names are of the form: <class>_children_get_<childName>

- Property getter names are of the form: <class>_properties_get_<propertyName>

- Property setter names are of the form: <class>_properties_set_<propertyName>

- Function names are of the form: <class>_functions_<functionName>

- In tool names, underscores are used only to delineate
  namespaces. The names of children, properties, and functions should
  be expressed with "camel case". The tools.json file has many correct
  examples.
  
- Tool descriptions are complete sentences, beginning with a
  capitalized word and ending with a period.
  
- Child, property, and return value descriptions are phrases,
  beginning with a lowercase letter and ending without a period.
  
