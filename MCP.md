MCP (Model Context Protocol) is an open-source standard for connecting AI applications to external systems. Using MCP, AI applications like Claude or ChatGPT can connect to data sources (e.g. local files, databases), tools (e.g. search engines, calculators) and workflows (e.g. specialized prompts)—enabling them to access key information and perform tasks.

Simply said, MCP offers a clear unified way through which various AI agents from different providers can connect to and execute things on an external tool e.g. a database or a different application. This simpleifes automation as instead of writing code thats tightly coupled to a given provider, you write general code that can be used by an agent from any provider e.g. OpenAI or Claude

![[Pasted image 20260918112853.png]]
# How does it work?
In order to use MCP, you begin by picking an MCP SDK e.g. fastmcp using python or @modelcontextprotocol/sdk npm package using JavaScript.

Demonstrated here is a simple fastmcp implementation of an MCP tool.

```python
import sqlite3
from fastmcp import FastMCP

# Initialize the MCP Server
mcp = FastMCP("Customer-Database-Tools")

DB_PATH = "company.db"

@mcp.tool()
def get_inactive_customers(months_inactive: int = 2) -> list[dict]:
    """
    Finds customers whose accounts have had no activity for at least 
    the specified number of months (defaults to 2).
    """
    conn = sqlite3.connect(DB_PATH)
    conn.row_factory = sqlite3.Row  # Returns results as dictionary-like objects
    cursor = conn.cursor()

    # Custom SQL Query
    query = """
        SELECT customer_id, name, email, last_active_date
        FROM customers
        WHERE last_active_date <= date('now', '-' || ? || ' month')
        ORDER BY last_active_date ASC;
    """
    
    cursor.execute(query, (months_inactive,))
    rows = cursor.fetchall()
    conn.close()

    # Return structured dicts so the AI can read the data easily
    return [dict(row) for row in rows]

if __name__ == "__main__":
    mcp.run()
```

Using this, we are able to qu