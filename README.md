# ableton-mcp

This project is a harness for generating the JSON "tools/list" method
response given by an Ableton Live MCP server, including output
schemas. These MCP tools provide complete coverage of properties,
children, and functions of objects in the Ableton Live 12.2 API. Data
comes from the Live Object Model documentation in Cycling74's Max 9,
at https://docs.cycling74.com/apiref/lom/. Ableton Live 12.2 user
documentation is at
https://www.ableton.com/en/live-manual/12/welcome-to-live/.

One can use that JSON as a specification for tool functions. I'm
implementing those functions in a webapp that speaks to "Max for Live"
via its built-in NodeJS server. See
https://thiscontext.com/2021/06/05/ableton-livecoding-with-caffeine/.



