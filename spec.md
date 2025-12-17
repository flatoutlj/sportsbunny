# SportsBunny - Product Specification

## Overview
SportsBunny is an AI-powered sports analytics platform that enables users to generate professional-grade research reports and analytics through an intuitive drag-and-drop interface or natural language queries.

## Brand Identity

### Visual Design
- **Color Scheme**: Black (#0A0A0A) and Orange (#FF6B00)
- **Logo**: Cool sports-themed bunny mascot in the top-left navigation
- **Typography**: Modern, bold sans-serif (Inter)
- **Style**: Sleek, dark mode with vibrant orange accents

## Core Features

### 1. Report Builder (Demo Page)
**User Journey:**
1. User clicks "Demo" or "Get Started"
2. Lands on the Report Builder interface
3. Two main modes:
   - **Custom Build**: Drag and drop parameters
   - **Quick Start**: Choose from popular bets of the day

#### Custom Build Mode
**Interface Components:**
- **Left Sidebar**: Parameter Palette
  - Player selection (search/autocomplete)
  - Team selection
  - Date range picker
  - Stats to include (checkboxes)
  - Game time slots
  - Home/Away filter
  - Month filters (October vs other months)

- **Center Canvas**: Report Builder
  - Drag-and-drop zones for data blocks
  - Visual preview of report structure
  - Rearrangeable sections

- **Right Panel**: Live Preview
  - Real-time report preview
  - Export options (PNG, PDF, Share link)

**Available Parameters:**
```
Players:
- Search by name
- Filter by position (QB, RB, WR, etc.)
- Filter by team
- Multi-select for comparisons

Stats:
- Completion %
- Passing yards
- Touchdowns
- Interceptions
- Passer rating
- QBR
- Home/Away splits
- Time slot performance
- Monthly trends

Time Filters:
- Season selector (2024, 2023, 2022)
- Month breakdown
- Game time slots (1pm, 4pm, Primetime)
- Custom date ranges

Analysis Types:
- Trend Analysis
- Player Comparisons
- Performance by Conditions (weather, home/away, time)
- Historical Performance
- Predictive Insights
```

#### Quick Start Mode (Popular Bets)
**Interface:**
- **Today's Featured Bets** section
  - Auto-generated cards for trending games
  - One-click to generate relevant research

**Example Cards:**
```
┌─────────────────────────────────────┐
│ 🏈 TNF: Chiefs @ Bills             │
│ Mahomes Away Performance in Oct     │
│ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━   │
│ Popular Props:                      │
│ • Mahomes 275+ passing yards        │
│ • Allen 2+ passing TDs              │
│                                     │
│ [Generate Research Report] →        │
└─────────────────────────────────────┘
```

**Auto-Generated Research Includes:**
- QB accuracy trends (October vs other months)
- Performance by game time slot
- Head-to-head history
- Weather impact (if outdoor game)
- Recent form (last 5 games)
- Injury report impacts
- Defensive matchup analysis

### 2. Report Output

**Generated Report Structure:**
```
┌─────────────────────────────────────────────┐
│  SPORTSBUNNY RESEARCH REPORT                │
│  Generated: Dec 12, 2024 7:00 PM ET        │
├─────────────────────────────────────────────┤
│                                             │
│  PATRICK MAHOMES - QB ANALYSIS              │
│  Away Games | October Performance           │
│                                             │
│  ┌───────────────────────────────────┐     │
│  │ OCTOBER VS OTHER MONTHS           │     │
│  │                                   │     │
│  │ October:    68.3% completion      │     │
│  │ Other:      65.1% completion      │     │
│  │ Difference: +3.2%                 │     │
│  │                                   │     │
│  │ [Bar Chart Visualization]         │     │
│  └───────────────────────────────────┘     │
│                                             │
│  ┌───────────────────────────────────┐     │
│  │ PERFORMANCE BY TIME SLOT          │     │
│  │                                   │     │
│  │ Early (1pm):     64.2%            │     │
│  │ Afternoon (4pm): 66.5%            │     │
│  │ Primetime:       69.8% ⭐         │     │
│  │                                   │     │
│  │ [Line Chart Trend]                │     │
│  └───────────────────────────────────┘     │
│                                             │
│  KEY INSIGHTS                               │
│  • Significantly better in primetime        │
│  • October boost (+3.2% accuracy)          │
│  • 12/3 TD/INT in October away games       │
│                                             │
│  RECOMMENDATION: ✅ FAVORABLE              │
│                                             │
│  [Export PNG] [Export PDF] [Share Link]    │
└─────────────────────────────────────────────┘
```

## Technical Architecture

### Frontend Pages
```
/                       → Landing page (existing)
/demo                   → Report Builder interface
/reports/:id            → View generated report
/popular-bets           → Quick start templates
/qb-analysis            → Specific QB analysis tool
```

### Component Structure
```
/app
├── demo/
│   ├── page.tsx                    → Main demo page
│   ├── components/
│   │   ├── ParameterPalette.tsx    → Left sidebar
│   │   ├── ReportCanvas.tsx        → Center drag-drop area
│   │   ├── LivePreview.tsx         → Right preview panel
│   │   ├── PopularBets.tsx         → Quick start cards
│   │   └── DataBlock.tsx           → Draggable parameter block
│   └── layout.tsx
├── reports/
│   └── [id]/
│       └── page.tsx                → Report view page
└── popular-bets/
    └── page.tsx                    → Browse all popular bets
```

## User Workflows

### Workflow 1: Custom QB Analysis
1. User navigates to `/demo`
2. Selects "Custom Build" mode
3. Searches for "Patrick Mahomes"
4. Drags "October vs Other Months" parameter
5. Drags "Time Slot Performance" parameter
6. Drags "Away Games Filter" parameter
7. Clicks "Generate Report"
8. System fetches data from ESPN API
9. Analytics engine calculates stats
10. Report is generated and displayed
11. User can export or share

### Workflow 2: Popular Bet Quick Research
1. User navigates to `/demo`
2. Sees "Today's Games" section
3. Clicks "Generate Research" on Chiefs @ Bills
4. System automatically:
   - Identifies QBs (Mahomes, Allen)
   - Pulls relevant historical data
   - Calculates October trends
   - Analyzes time slot performance
   - Generates head-to-head comparison
5. Complete research report displayed
6. User reviews and exports

## Data Requirements

### ESPN API Integration
- Game schedules and scores
- Player statistics (per game)
- Team data
- Historical game logs

### Analytics Calculations
- Monthly aggregations (October vs others)
- Time slot groupings (1pm, 4pm, 8pm+)
- Home/Away splits
- Trend analysis (rolling averages)
- Completion percentage calculations
- Passer rating calculations

## Milestones

### Milestone 1: Bunny Logo & Brand Update
**Time**: 1-2 hours
- [ ] Design or source sports bunny mascot SVG
- [ ] Update navigation logo
- [ ] Ensure responsive sizing

### Milestone 2: Demo Page Foundation
**Time**: 3-4 hours
- [ ] Create `/demo` route
- [ ] Build basic layout (3-column: palette, canvas, preview)
- [ ] Implement tab switching (Custom Build vs Popular Bets)
- [ ] Add basic styling with black/orange theme

### Milestone 3: Parameter Palette
**Time**: 4-5 hours
- [ ] Player search component with autocomplete
- [ ] Date range picker
- [ ] Stats checkboxes (completion %, yards, TDs, etc.)
- [ ] Time slot selector
- [ ] Month filter (October vs others)
- [ ] Draggable parameter blocks

### Milestone 4: Report Canvas
**Time**: 5-6 hours
- [ ] Drag-and-drop zones with react-dnd
- [ ] Visual feedback for drop areas
- [ ] Rearrangeable sections
- [ ] Remove/edit parameter blocks
- [ ] "Generate Report" button

### Milestone 5: Popular Bets Feature
**Time**: 3-4 hours
- [ ] Today's games API integration
- [ ] Auto-generate bet cards
- [ ] Popular props suggestions
- [ ] One-click report generation
- [ ] Template system for common analyses

### Milestone 6: Backend Integration
**Time**: 6-8 hours
- [ ] Extend ESPN API client for QB stats
- [ ] Monthly aggregation logic
- [ ] Time slot categorization
- [ ] Home/away filtering
- [ ] Report generation endpoint
- [ ] Caching layer (Solution 1 from plan)

### Milestone 7: Report Generation & Display
**Time**: 5-6 hours
- [ ] Report template components
- [ ] Chart integration (Recharts)
- [ ] Data visualization (bar charts, line charts)
- [ ] Key insights generation (AI-powered?)
- [ ] Export to PNG/PDF
- [ ] Share link generation

### Milestone 8: Report View Page
**Time**: 2-3 hours
- [ ] Create `/reports/[id]` route
- [ ] Display generated report
- [ ] Social sharing meta tags
- [ ] Print-friendly styling

## Success Metrics

### User Experience
- Time to generate first report: < 30 seconds
- Report generation success rate: > 95%
- User satisfaction with insights: > 4.5/5 stars

### Performance
- Page load time: < 2 seconds
- Report generation time: < 5 seconds
- API response time: < 1 second

### Engagement
- % of users who generate > 1 report: > 60%
- % of users who export reports: > 40%
- Return user rate: > 50%

## Future Enhancements

### Phase 2 Features
- [ ] Save custom templates
- [ ] Workspace for managing reports
- [ ] Real-time data updates during games
- [ ] Mobile-optimized report builder
- [ ] Collaborative reports (share with friends)
- [ ] AI-powered bet recommendations
- [ ] Integration with sportsbooks (odds display)
- [ ] Video graphics generation

### Phase 3 Features
- [ ] Machine learning predictions
- [ ] Historical accuracy tracking
- [ ] Community-shared templates
- [ ] Discord/Slack integration
- [ ] Premium features (more sports, more stats)
- [ ] API access for developers

## Technical Decisions

### State Management
- Use Zustand for report builder state
- React Query for data fetching
- Local storage for draft reports

### Drag & Drop
- Use `react-dnd` or `dnd-kit` for drag-and-drop
- Smooth animations with Framer Motion

### Charts
- Recharts for data visualization
- Custom color scheme (black/orange)

### Export
- `html2canvas` for PNG export
- `jsPDF` for PDF export
- Generate unique shareable URLs

## Notes
- Start with Solution 1 (Direct API) from the implementation plan
- Focus on NFL QB analysis as the initial use case
- Expand to other sports/positions later
- Ensure mobile responsiveness from the start
- Keep the UI simple and intuitive
- Dark theme throughout for consistency
