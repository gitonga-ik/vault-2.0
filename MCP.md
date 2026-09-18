MCP (Model Context Protocol) is an open-source standard for connecting AI applications to external systems. Using MCP, AI applications like Claude or ChatGPT can connect to data sources (e.g. local files, databases), tools (e.g. search engines, calculators) and workflows (e.g. specialized prompts)—enabling them to access key information and perform tasks.

Simply said, MCP offers a clear unified way through which various AI agents from different providers can connect to and execute things on an external tool e.g. a database or a different application. This simpleifes automation as instead of writing code thats tightly coupled to a given provider, you write general code that can be used by an agent from any provider e.g. OpenAI or Claude

![[Pasted image 20260918112853.png]]
# How does it work?
In order to use MCP, you begin by picking an MCP SDK e.g. fastmcp using python or 