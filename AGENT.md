# AGENT.md

## Read the README

In a new conversation, read the README before doing anything else.

## Using MCP

- First step: Check what MCP tools are actually available from
  connected servers (not the JSON schemas). DO NOT ATTEMPT to use a
  tool that you have not confirmed is available from a connected MCP
  server.

- If the needed tool is missing: Suggest that the user implement it,
  referencing the JSON schema files as specifications.

The JSON schema files in the tools directory describe MCP tools that
we are developing. They aren't necessarily active in any MCP servers
to which you are connected. The ONLY source of truth about which MCP
tools you can call is provided by connected MCP servers. Do not take
the existence of a tool in a JSON schema file, on its own, as evidence
that you can call that tool. You should check the real tools list
first.

When it seems like an Ableton MCP tool is missing from the Ableton MCP
server during conversation, suggest that the user implement it. The
complete space of possible tools is covered by the JSON schema files
in the tools directory.

Usually, if a tool call times out, it's because the user is debugging
the tool call on the MCP server side.

## Using Canonical Paths for Ableton Objects in MCP tool calls

IMPORTANT: Many Ableton Live objects can be referenced by their
canonical path instead of requiring object ID lookups. This is
especially useful for predictable objects like scenes:

- First scene: `live_set scenes 0`
- Second scene: `live_set scenes 1`
- First track: `live_set tracks 0`

Always prefer canonical paths when possible, instead of suggesting
tools to look up object IDs first. For example, to rename the first
scene, you only need `scene_properties_set_name` with the canonical
path `live_set scenes 0`.

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
beginning of the function. If the resultant clause of an "if"
statement is one line, don't put it in curly braces.

Never bundle sources. Never use webpack or anything like it.

## Editing tools JSON schema files

When editing the tools JSON schema files:

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
  be expressed with "camel case". The JSON files have many correct
  examples.
  
- Tool descriptions are complete sentences, beginning with a
  capitalized word and ending with a period.
  
- Child, property, and return value descriptions are phrases,
  beginning with an uncapitalized word and ending without a period.
  
