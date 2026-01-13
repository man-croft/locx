# locx

AI-powered Farcaster mini app that breaks echo chambers by surfacing counter-narratives to trending topics.

## What is locx?

locx helps you discover diverse perspectives on Farcaster. When a topic trends, the app analyzes dominant viewpoints and finds counter-narratives from Farcaster, Twitter/X, and news sources. You can share these perspectives back to Farcaster and mint NFT "Insight Tokens" to record your echo chamber breaking activity.

The app uses a freemium model: free features for everyone, premium tier for advanced capabilities, plus NFT minting and subscription revenue.

---

## Architecture

### Frontend
- **Next.js 14** + React 18 for performance and SSR
- Single-page app with multiple views (trends, echoes, premium, FAQ)
- Mobile-first design optimized for Farcaster users
- Client-side polling for real-time trending updates

### Backend
- **Next.js API routes** for all backend logic
- Modular endpoints for each feature:
  - `trending` - Fetch trending casts
  - `ai-analysis` - Sentiment and viewpoint analysis
  - `cross-platform` - Search Twitter, news, external sources
  - `echo` - Recast to Farcaster
  - `mint-nft` - Create Insight Tokens
  - `monetization` - Premium tier management
- **OpenAI GPT-3.5-turbo** for AI analysis
- **Neynar API** for Farcaster data

### User Flow
1. App fetches trending Farcaster topics
2. AI analyzes dominant sentiment/viewpoint
3. Cross-platform search finds counter-narratives
4. User can echo topic back or mint NFT
5. Premium features require tier verification

### Authentication
- Wallet-based auth (Ethereum)
- Direct Farcaster account integration
- Subscription tiers: Free, Premium, Pro

### Monetization
- Premium features behind paywall
- Insight Token NFTs (variable pricing)
- USDC payments on Base network
- Future platform partnerships

---

## Dependencies

### Social APIs
- **Neynar**: Farcaster data and trending casts
- **Twitter/X API v2**: Cross-platform content
- **NewsAPI**: News source aggregation

### AI
- **OpenAI GPT-3.5-turbo**: Sentiment, bias detection, counter-narratives
- Custom analysis prompts

### Blockchain
- **Viem** + **Wagmi**: Ethereum wallet integration
- **Base Network**: Low-cost NFT minting and USDC
- **USDC Contract**: Stablecoin payments

### Infrastructure
- **Next.js**: Full-stack framework
- **Vercel**: Deployment platform
- **Node-fetch**: HTTP requests

### Media
- **DiceBear API**: Avatar generation for NFTs
- **Farcaster Protocol**: Mini-app integration

### Environment Variables
```
NEYNAR_API_KEY=<farcaster-data-access>
OPENAI_API_KEY=<ai-analysis>
X_BEARER_TOKEN=<twitter-api>
NEWS_API_KEY=<news-aggregation>
```

---

## Key Features

- 🔄 Real-time trending topic analysis
- 🤖 AI-powered counter-narrative discovery
- 🌐 Cross-platform perspective surfacing
- 📝 One-click echo to Farcaster
- 🎖️ NFT minting for milestones
- 💎 Premium tier features
- 📱 Mobile-optimized experience

---

## Getting Started

### Prerequisites
- Node.js 18+
- Yarn or npm
- Ethereum wallet (MetaMask recommended)
- API keys for: Neynar, OpenAI, Twitter/X, NewsAPI

### Installation
```bash
git clone https://github.com/investorphem/locx.git
cd locx
yarn install
```

### Configuration
Create a `.env.local` file:
```bash
NEYNAR_API_KEY=your_key_here
OPENAI_API_KEY=your_key_here
X_BEARER_TOKEN=your_key_here
NEWS_API_KEY=your_key_here
```

### Development
```bash
yarn dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser.

### Production
```bash
yarn build
yarn start
```

---

## Project Structure

```
locx/
├── pages/              # Next.js pages and API routes
│   ├── api/           # Backend API endpoints
│   ├── index.js       # Home page
│   ├── faq.js         # FAQ page
│   └── _app.js        # App wrapper
├── components/        # React components
├── lib/              # Utilities and helpers
├── public/           # Static assets
├── styles/           # Global styles
├── data/             # Static data
├── db/               # Database schema
└── package.json      # Dependencies
```

---

## API Endpoints

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/api/trending` | GET | Fetch trending casts |
| `/api/ai-analysis` | POST | Analyze sentiment/viewpoint |
| `/api/cross-platform` | POST | Search counter-narratives |
| `/api/echo` | POST | Recast to Farcaster |
| `/api/mint-nft` | POST | Create Insight Token |
| `/api/user-echoes` | GET | Get user's echo history |
| `/api/premium-check` | GET | Verify premium status |

---

## Deployment

The app is optimized for **Vercel** deployment:

1. Push code to GitHub
2. Connect repository to Vercel
3. Add environment variables in Vercel dashboard
4. Deploy with one click

---

## License

MIT

## Contributing

Contributions welcome! Please open an issue or pull request.
