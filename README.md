# ableton-mcp

This project is a harness for generating the JSON "tools/list" method
response given by an Ableton Live MCP server, including output
schemas. These MCP tools provide complete coverage of children,
properties, and functions of objects in the Ableton Live 12.2
API. Data comes from the Live Object Model documentation in
Cycling74's Max 9, at https://docs.cycling74.com/apiref/lom/. Ableton
Live 12.2 user documentation is at
https://ableton.com/en/live-manual/12/welcome-to-live/.

JSON schemas for the tools are AI-generated, and serve as
specifications for actual tool functions. I'm implementing those
functions in an MCP server webapp that speaks to "Max for Live" via
its built-in NodeJS server. See
https://thiscontext.com/2021/06/05/ableton-livecoding-with-caffeine/.



