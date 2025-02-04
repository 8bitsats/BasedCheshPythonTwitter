- 🔒 Advanced Rate Limiting
  - Cookie-based authentication
  - State persistence between sessions
  - Automatic rate limit handling
  - Request queueing and retry logic

- 💰 Blockchain Integration
  - Real-time wallet status updates
  - Base blockchain monitoring
  - Token balance tracking
  - Transaction history

- 🤖 Dual AI Integration
  - Perplexity AI for market analysis
  - Grok AI for trend insights
  - Combined AI perspectives
  - Themed content generation

- 🎭 Enhanced Engagement
  - Poll creation and tracking
  - Media-rich tweets
  - Automated responses
  - DeFi-themed riddles

- 🔍 Advanced Scraping
  - Detailed tweet analytics
  - Poll result tracking
  - Media content extraction
  - Enhanced mention processing

## Setup

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Configure API keys in `src/game_sdk/config.py`:
- Twitter API credentials
- Perplexity API key
- Twitter login credentials (for cookie-based auth)

3. The wallet integration uses the Base blockchain configuration from `src/game_sdk/game/wallet.py`

## Usage

```python
from twitter import CheshireTwitterClient

# Initialize client
client = CheshireTwitterClient()

# Basic Operations
client.post_wallet_update()
client.post_market_insight()
client.post_riddle()

# Advanced Features
# Create a poll
poll_result = client.create_poll(
    question="What's your take on Base Chain? 🤔",
    options=[
        "Bullish! 🚀",
        "Need more info 🤔",
        "Just watching 👀",
        "Not convinced 🤷‍♂️"
    ],
    duration_minutes=1440  # 24 hours
)

# Get detailed tweet info
import asyncio
async def get_poll_details():
    details = await client.get_tweet_with_poll("tweet_id_here")
    print(f"Poll results: {details}")

# Get enhanced mentions
mentions = client.get_mentions(5)
for mention in mentions:
    print(f"From @{mention['user']}:")
    print(f"- Text: {mention['text']}")
    print(f"- Has media: {mention['has_media']}")
    print(f"- Is reply: {mention['is_reply']}")
    print(f"- Hashtags: {mention['hashtags']}")
```

## Advanced Features

### Rate Limiting System
```python
# The rate limiter automatically handles:
- Request tracking with timestamps
- State persistence between sessions
- Dynamic wait time calculation
- Cookie-based session management
- Automatic request queueing
```

### AI Integration
```python
# Market insights combine multiple AI perspectives:
- Perplexity AI for technical analysis
- Grok AI for trend prediction
- Combined insights for better decision making
- Themed content generation
```

### Enhanced Scraping
```python
# Advanced data extraction capabilities:
- Full poll details and results
- Media content metadata
- Engagement metrics
- User interaction patterns
```

### Wallet Integration
```python
# Comprehensive blockchain monitoring:
- Real-time balance updates
- Token tracking
- Transaction history
- Chain-specific metrics
```

## Wallet Integration

Automatically fetches and formats:
- Wallet address
- Chain information
- Current balance
- Token holdings

## Market Insights

Uses Perplexity AI to generate:
- Market analysis
- DeFi trends
- Base blockchain updates
- Themed commentary

## File Structure

```
examples/hosted_agent/
├── twitter.py          # Main client implementation
├── requirements.txt    # Dependencies
└── README.md          # Documentation
```

## Error Handling

- Comprehensive error logging
- Graceful fallbacks for API failures
- Rate limit violation prevention
- Connection retry logic

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

### Development Guidelines
- Use async/await for network operations
- Implement proper error handling
- Add comprehensive logging
- Include unit tests
- Document new features

## License

This project is licensed under the MIT License - see the LICENSE file for details.
