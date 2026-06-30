# M13 AAA-Élites Hockey - Playoffs Player Stats

This repository tracks and displays individual player statistics for the M13 AAA-Élites Hockey playoffs in the Hockey Experts division.

## Overview

- **Division**: Hockey Experts (LHEQ)
- **Season**: 2025-2026 Playoffs
- **Duration**: April 3-5, 2026
- **Total Games**: 7
- **Total Teams**: 7

## Website

The live statistics are available at: **https://jee2727.github.io/M13-AAA-lites---Playoffs-Player-Stats---Division-Hockey-Experts-/**

## How to Add Game Data

### File Structure

All game data is stored in `games.json`. Each game entry should follow this format:

```json
{
  "games": [
    {
      "gameId": 1,
      "date": "2026-04-03",
      "homeTeam": "Team Name",
      "awayTeam": "Team Name",
      "homeScore": 3,
      "awayScore": 2,
      "plays": [
        {
          "playerName": "Player Name",
          "team": "Team Name",
          "goals": 1,
          "assists": 0
        },
        {
          "playerName": "Another Player",
          "team": "Team Name",
          "goals": 0,
          "assists": 2
        }
      ]
    }
  ]
}
```

### Instructions for Adding a Game

1. Open `games.json`
2. Add a new game object to the `games` array with:
   - **gameId**: Sequential number (1-7)
   - **date**: Game date in YYYY-MM-DD format
   - **homeTeam**: Home team name
   - **awayTeam**: Away team name
   - **homeScore**: Final score for home team
   - **awayScore**: Final score for away team
   - **plays**: Array of player performances, including:
     - **playerName**: Player's full name
     - **team**: Team the player plays for
     - **goals**: Number of goals scored
     - **assists**: Number of assists

3. Commit and push your changes
4. The GitHub Pages site will automatically update within a few seconds

## Statistics Displayed

The webpage displays the following player statistics:

- **#**: Player ranking
- **Player**: Player's name
- **GP**: Games Played (number of games with recorded stats)
- **G**: Goals scored
- **A**: Assists
- **PTS**: Total Points (Goals + Assists)

### Sorting

Players are automatically sorted by:
1. **Points (PTS)** - Highest to Lowest
2. **Goals (G)** - Used as tiebreaker when players have equal points

## Technology

- **Frontend**: HTML5, CSS3, JavaScript (vanilla)
- **Data Format**: JSON
- **Hosting**: GitHub Pages
- **CI/CD**: GitHub Actions

## Files

- `index.html` - Main webpage with stats display and calculation logic
- `games.json` - Game data storage
- `.github/workflows/pages.yml` - GitHub Pages deployment workflow
- `README.md` - This documentation file

## How Stats Are Calculated

1. For each game in `games.json`, the system reads all player performances
2. Players are grouped by name, aggregating their stats across all games
3. Games Played (GP) is calculated by counting unique games where the player has recorded stats
4. Points are calculated as: Goals + Assists
5. Final list is sorted by Points (descending), then Goals (descending)

## Notes

- Player names are case-sensitive and should be consistent across all games
- Ensure team names match exactly across all game entries
- Only players with recorded stats (goals or assists) are included in the rankings
