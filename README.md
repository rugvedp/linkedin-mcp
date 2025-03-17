# LinkedIn Profile Analyzer MCP

A powerful LinkedIn profile analyzer MCP (Machine Control Protocol) server that interacts with LinkedIn's API to fetch, analyze, and manage LinkedIn posts data. This MCP is specifically designed to work with Claude AI.

## Features

- Fetch and store LinkedIn posts for any public profile
- Search through posts with keyword filtering
- Get top performing posts based on engagement metrics
- Filter posts by date range
- Paginated access to stored posts
- Easy integration with Claude AI

## Prerequisites

- Python 3.7+
- RapidAPI key for LinkedIn Data API
- Claude AI access

## Getting Started

### 1. Get RapidAPI Key

1. Visit [LinkedIn Data API on RapidAPI](https://rapidapi.com/rockapis-rockapis-default/api/linkedin-data-api)
2. Sign up or log in to RapidAPI
3. Subscribe to the LinkedIn Data API
4. Copy your RapidAPI key from the dashboard

### 2. Installation

1. Clone the repository:
```bash
git clone https://github.com/rugvedp/linkedin-mcp.git
cd linkedin-mcp
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
   - Create a `.env` file
   - Add your RapidAPI key:
```env
RAPIDAPI_KEY=your_rapidapi_key_here
```

## Project Structure

```
linkedin-mcp/
├── main.py              # Main MCP server implementation
├── mcp.json            # MCP configuration file
├── requirements.txt    # Python dependencies
├── .env               # Environment variables
└── README.md          # Documentation
```

## MCP Configuration

The `mcp.json` file configures the LinkedIn MCP server:

```json
{
  "mcpServers": {
    "LinkedIn Updated": {
      "command": "uv",
      "args": [
        "run",
        "--with",
        "mcp[cli]",
        "mcp",
        "run",
        "path/to/your/script.py"
      ]
    }
  }
}
```

Make sure to update the path in `args` to match your local file location.

## Available Tools

### 1. fetch_and_save_linkedin_posts
Fetches LinkedIn posts for a given username and saves them locally.
```python
fetch_and_save_linkedin_posts(username: str) -> str
```

### 2. get_saved_posts
Retrieves saved posts with pagination support.
```python
get_saved_posts(start: int = 0, limit: int = 10) -> dict
```

### 3. search_posts
Searches posts for specific keywords.
```python
search_posts(keyword: str) -> dict
```

### 4. get_top_posts
Returns top performing posts based on engagement metrics.
```python
get_top_posts(metric: str = "Like Count", top_n: int = 5) -> dict
```

### 5. get_posts_by_date
Filters posts within a specified date range.
```python
get_posts_by_date(start_date: str, end_date: str) -> dict
```

## Using with Claude

1. Initialize the MCP server in your conversation with Claude
2. Use the available tools through natural language commands
3. Claude will help you interact with LinkedIn data using these tools

## API Integration

This project uses the following endpoint from the LinkedIn Data API:

- `GET /get-profile-posts`: Fetches posts from a LinkedIn profile
  - Base URL: `https://linkedin-data-api.p.rapidapi.com`
  - Required Headers:
    - `x-rapidapi-key`: Your RapidAPI key
    - `x-rapidapi-host`: `linkedin-data-api.p.rapidapi.com`

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

[Rugved Patil](https://github.com/rugvedp)

## Repository

[linkedin-mcp](https://github.com/rugvedp/linkedin-mcp.git)

## Acknowledgments

- RapidAPI for providing LinkedIn data access
- Anthropic for Claude AI capabilities

## Project Structure 
