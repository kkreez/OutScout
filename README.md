# TasteCraft: AI-Powered Personal Dining Curator

A beautiful, interactive web application that uses AI to generate personalized restaurant recommendations based on your dining preferences, history, lifestyle, and context.

## Features

- **4-Step Guided Questionnaire**: Intuitive form covering cuisines, dietary needs, dining history, lifestyle preferences, and location
- **AI-Powered Recommendations**: Leverages Claude 3.5 Sonnet to generate 5 highly personalized restaurant suggestions
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Warm, Elegant UI**: Custom color palette with smooth interactions and animations
- **Secure Backend**: API key protected with serverless backend (Vercel Functions)

## Tech Stack

- **Frontend**: React 18, vanilla CSS with CSS variables
- **Backend**: Serverless function (Vercel Functions)
- **AI**: Anthropic Claude API (claude-3-5-sonnet-20241022)
- **Styling**: Custom CSS with accessible color palette and animations
- **Fonts**: Playfair Display (serif), DM Sans (sans-serif)

## Getting Started

### Prerequisites

- Node.js 18+
- Anthropic API key

### Installation

1. Clone the repository:
```bash
git clone https://github.com/kkreez/OutScout.git
cd OutScout
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env.local` file and add your Anthropic API key:
```bash
cp .env.example .env.local
# Edit .env.local and add your ANTHROPIC_API_KEY
```

4. Start the development server:
```bash
npm run dev
```

5. Open [http://localhost:3000](http://localhost:3000) in your browser

## Deployment

### Deploy to Vercel

1. Push your code to GitHub
2. Go to [vercel.com](https://vercel.com)
3. Import the OutScout repository
4. Add the `ANTHROPIC_API_KEY` environment variable in Vercel project settings
5. Deploy!

Environment variables will be automatically used by the serverless function.

## How It Works

### User Flow

1. **Step 1**: Select favorite cuisines and dietary preferences
2. **Step 2**: Share dining history, favorite dishes, and spending preferences
3. **Step 3**: Describe your vibe, social interests, and lifestyle
4. **Step 4**: Provide location and special context
5. **Results**: Receive 5 personalized recommendations with match scores, tags, and tasting notes

### Behind the Scenes

- User profile data is compiled into a detailed prompt
- Prompt is sent securely to `/api/recommendations` endpoint
- Serverless function calls Anthropic Claude API with your API key
- Claude returns 5 JSON-formatted recommendations
- Frontend parses and beautifully renders the results

## API Endpoint

### POST `/api/recommendations`

Request:
```json
{
  "prompt": "Your detailed dining curator prompt..."
}
```

Response:
```json
{
  "text": "[JSON array of 5 recommendations]"
}
```

## Security

- API keys are stored as environment variables (never committed to repo)
- All API calls go through the serverless backend, not directly from the browser
- The frontend never has access to your Anthropic API key

## Customization

Edit `CUISINES`, `DIETARY`, `VIBES`, and `SOCIAL_INTERESTS` arrays in `index.html` to customize the options available to users.

Modify the prompt template in the `buildPrompt()` function to change how recommendations are generated.

## License

MIT

## Author

Created with ❤️ for food lovers everywhere.
