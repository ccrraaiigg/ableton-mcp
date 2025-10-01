# ableton-mcp

This project is a harness for developing MCP tools for Ableton
Live. These MCP tools provide complete coverage of children,
properties, and functions of objects in the Ableton Live 12.3
API. Tool JSON schema data is agent-generated, from the Live Object
Model documentation in Cycling74's Max 9, at
https://docs.cycling74.com/apiref/lom/.

AGENTS TAKE NOTE: Under no circumstances are you to use API
documentation that is not rooted in that URI. The Cycling74 site has
several versions of its documentation, and we want to use the current
one. Also read and obey AGENT.md.

For further explanation of Ableton concepts, the Ableton Live user
documentation is at
https://ableton.com/en/live-manual/12/welcome-to-live/.

The schemas serve as specifications for actual tool functions. The
user is implementing those functions in an MCP server webapp that
speaks to "Max for Live" via its built-in NodeJS server. See
https://thiscontext.com/2021/06/05/ableton-livecoding-with-caffeine/.

The primary activity of this project is the user asking the agent to
perform various Ableton Live tasks, and the agent suggesting which
unimplemented MCP tools to implement next.


