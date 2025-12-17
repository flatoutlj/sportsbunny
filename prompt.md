# SportsBunny QB Analysis - Use Case Prompt

## The Scenario
A sports bettor is preparing for a Halloween night football (NFL) game. For his own superstitions, our bettor wants to check the away team's quarterback accuracy trends for games in October vs other playing months, and historically at which game time slots they perform better in.

## What the Bettor Needs

### Primary Analysis
1. **QB Accuracy by Month**
   - Compare October games vs. all other months
   - Key metrics: Completion %, Passer Rating, QBR
   - Focus: Away team quarterbacks only

2. **QB Performance by Game Time Slot**
   - Early games (1pm ET)
   - Afternoon games (4pm ET)
   - Primetime games (8pm+ ET / Sunday Night / Monday Night / Thursday Night)
   - Key metrics: Same as above

### Example Questions to Answer
- "Does Patrick Mahomes have better completion percentage in October away games?"
- "How does Josh Allen perform in primetime away games vs. afternoon away games?"
- "Is Jalen Hurts more accurate in October vs. other months when playing on the road?"

## Data Requirements

### Essential Stats
- Completion percentage (completions / attempts)
- Passing yards per game
- Touchdowns and interceptions
- Passer rating
- QBR (if available)

### Filtering Criteria
- **Month**: October (month 10) vs. Other months (1-9, 11-12)
- **Home/Away**: Away games only
- **Time Slot**: Early (1pm), Afternoon (4pm), Primetime (8pm+)
- **Position**: Quarterbacks only
- **Historical Range**: At least current season, ideally 2-3 seasons

## Use Case Flow

1. User opens the QB Analysis page
2. User enters or searches for QB name (e.g., "Patrick Mahomes")
3. User selects seasons to analyze (default: current + last season)
4. User clicks "Analyze"
5. System displays:
   - Table comparing October vs. Other Months stats
   - Table showing performance by time slot (Early/Afternoon/Primetime)
   - Charts visualizing completion % and passer rating trends
   - Key insights (e.g., "12% better in October primetime games")

## Success Criteria

The feature is successful if:
- ✅ Bettor can quickly see October vs. other months comparison
- ✅ Bettor can identify which time slots the QB performs best in
- ✅ Data is filtered for away games only
- ✅ Results load in < 5 seconds
- ✅ Stats are accurate and verifiable against official NFL data
- ✅ UI is simple and easy to understand

## Implementation Notes

### For Solution 1 (MVP)
- Start with current season only if multi-season data is complex
- Use simple tables and bar charts (Recharts)
- Manual QB search (no autocomplete needed for MVP)
- Show only essential stats (completion %, yards, TD/INT, passer rating)

### For Future Iterations
- Add autocomplete player search
- Include opponent defense strength metrics
- Add weather conditions for outdoor games
- Show trend lines over multiple seasons
- Add "export to image" for sharing on social media
- Include Vegas betting lines correlation

## Sample Output

### October vs. Other Months (Away Games)
| Metric | October | Other Months | Difference |
|--------|---------|--------------|------------|
| Games | 4 | 12 | - |
| Completion % | 68.3% | 65.1% | +3.2% |
| Pass Yards/G | 287 | 265 | +22 |
| TD/INT | 12/3 | 28/8 | Better |
| Passer Rating | 102.4 | 95.7 | +6.7 |

### Performance by Time Slot (Away Games Only)
| Metric | Early (1pm) | Afternoon (4pm) | Primetime (8pm+) |
|--------|-------------|-----------------|------------------|
| Games | 8 | 6 | 10 |
| Completion % | 64.2% | 66.5% | 69.8% |
| Pass Yards/G | 255 | 278 | 295 |
| Passer Rating | 92.3 | 97.1 | 104.2 |

**Key Insight**: This QB performs significantly better in primetime away games, especially in October.

---

*Edit this file to add your specific requirements, questions, or preferences before implementation begins.*