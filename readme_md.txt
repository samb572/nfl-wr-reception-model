# NFL WR Reception Betting Model

A sophisticated NFL wide receiver reception prediction model built with coverage-specific analytics and real-time defensive matchup analysis.

## Features

- **204+ Qualified Players**: All WR/TE with 100+ routes from 2024 season
- **32 NFL Defenses**: Complete coverage frequency and defensive stats
- **Coverage-Specific Analytics**: Man, Cover 2, Cover 3, Cover 4, Cover 6 breakdowns
- **Intelligent Autocomplete**: Fast player and team search functionality
- **Advanced Formula**: Coverage frequency weighted calculations
- **Mobile Responsive**: Works perfectly on all devices

## How It Works

The model analyzes four key inputs:
1. **Player Name** - Select from qualified WR/TE players
2. **Opponent Defense** - Choose the opposing team
3. **Game Context** - Expected game script (1-5 scale)
4. **Betting Line** - Sportsbook O/U reception line

### Algorithm

The model uses a sophisticated formula that weights player performance against specific coverage types based on how frequently the opposing defense runs those coverages:

```
Base Score = 
  (0.35 × Coverage_Adj_TPRR²) + 
  (0.25 × Normalized_Sep_Score²) + 
  (0.20 × Volume_Factor) + 
  (0.15 × Matchup_Factor) + 
  (0.10 × Game_Context_Factor)

Final Score = Base Score × TPRR_Quality_Multiplier
```

Key innovations:
- **Coverage Frequency Weighting**: Player stats are weighted by how often the defense runs each coverage
- **Separation Analysis**: Player separation scores against each coverage type
- **Target Share Integration**: Overall target share from route participation
- **Defensive Matchup Factor**: How generous the defense is compared to league averages

## Data Sources

All data extracted from 2024 NFL season analytics including:
- Target Per Route Run (TPRR) by coverage
- Separation scores by coverage
- Route participation and target share
- Defensive coverage frequencies
- Defensive TPRR and catch rates allowed

## Deployment

This app is designed for deployment on Vercel:

1. Push to GitHub repository
2. Connect to Vercel
3. Deploy automatically

No build process required - it's a static site with embedded data.

## File Structure

```
├── index.html          # Main application
├── js/
│   └── data.js         # Complete NFL dataset (204 players, 32 defenses)
├── package.json        # Project configuration
├── vercel.json         # Vercel deployment config
└── README.md          # This file
```

## Usage

1. Start typing a player name to see autocomplete suggestions
2. Select opposing defense from autocomplete
3. Choose expected game script (1-5 scale)
4. Enter the sportsbook reception line
5. Click "Calculate Reception Score" for analysis

The model provides:
- Coverage-weighted performance metrics
- Final reception score (0-100)
- Projected reception total
- Recommendation vs. betting line

## Contributing

This model uses actual NFL analytics data. To contribute:
1. Fork the repository
2. Make improvements to the algorithm or UI
3. Submit a pull request

## License

MIT License - See LICENSE file for details
