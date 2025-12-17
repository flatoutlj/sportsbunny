# SportsBunny - Development Milestones

## Project Vision
Build an intuitive drag-and-drop sports analytics platform where users can generate professional research reports by selecting parameters or choosing from popular bets of the day.

---

## 🎨 Milestone 1: Bunny Logo & Brand Update
**Status**: 🔴 Not Started
**Priority**: High
**Time Estimate**: 1-2 hours

### Tasks
- [ ] Design or source cool sports-themed bunny mascot SVG/image
- [ ] Create bunny logo component
- [ ] Update navigation to use bunny instead of "S" logo
- [ ] Ensure logo is responsive (mobile, tablet, desktop)
- [ ] Add hover effects and animations

### Deliverables
- Bunny logo SVG file in `/public/images/`
- Logo component at `/packages/ui/src/BunnyLogo.tsx`
- Updated navigation with new branding

---

## 🏗️ Milestone 2: Demo Page Foundation
**Status**: 🔴 Not Started
**Priority**: High
**Time Estimate**: 3-4 hours

### Tasks
- [ ] Create `/app/demo/page.tsx` route
- [ ] Build 3-column layout:
  - Left: Parameter Palette
  - Center: Report Canvas
  - Right: Live Preview
- [ ] Implement tab switching (Custom Build vs Popular Bets)
- [ ] Add responsive breakpoints
- [ ] Apply black/orange theme styling
- [ ] Add loading states and skeleton screens

### Deliverables
- Demo page accessible at `/demo`
- Responsive layout working on all screen sizes
- Tab navigation between modes

### Dependencies
- None

---

## 🎛️ Milestone 3: Parameter Palette
**Status**: 🔴 Not Started
**Priority**: High
**Time Estimate**: 4-5 hours

### Tasks
- [ ] Player search component with autocomplete
  - Integrate with ESPN API for player list
  - Typeahead suggestions
  - Multi-select for comparisons
- [ ] Date range picker component
- [ ] Stats checkboxes (completion %, yards, TDs, INTs, rating, QBR)
- [ ] Time slot selector (1pm, 4pm, Primetime)
- [ ] Month filter (October vs Other Months)
- [ ] Home/Away filter toggle
- [ ] Make all parameters draggable
- [ ] Visual feedback when dragging

### Deliverables
- Fully functional parameter palette
- All UI components styled with brand colors
- Smooth drag interactions

### Components to Build
- `PlayerSearch.tsx`
- `DateRangePicker.tsx`
- `StatsSelector.tsx`
- `TimeSlotFilter.tsx`
- `MonthFilter.tsx`
- `DraggableParameter.tsx`

### Dependencies
- Milestone 2 complete

---

## 🎨 Milestone 4: Report Canvas
**Status**: 🔴 Not Started
**Priority**: High
**Time Estimate**: 5-6 hours

### Tasks
- [ ] Install and configure `dnd-kit` or `react-dnd`
- [ ] Create drop zones for parameters
- [ ] Visual feedback for valid/invalid drop areas
- [ ] Rearrange blocks after dropping
- [ ] Edit parameter values inline
- [ ] Remove parameters from canvas
- [ ] "Generate Report" CTA button
- [ ] Empty state messaging
- [ ] Save draft to local storage

### Deliverables
- Working drag-and-drop canvas
- Smooth animations and transitions
- Intuitive UX for building reports

### Components to Build
- `ReportCanvas.tsx`
- `DropZone.tsx`
- `ParameterBlock.tsx`
- `GenerateButton.tsx`

### Dependencies
- Milestone 3 complete

---

## ⚡ Milestone 5: Popular Bets Feature
**Status**: 🔴 Not Started
**Priority**: Medium
**Time Estimate**: 3-4 hours

### Tasks
- [ ] Fetch today's NFL games from ESPN API
- [ ] Identify featured games (primetime, rivalry, etc.)
- [ ] Auto-generate bet cards with:
  - Game matchup
  - Key players (QBs)
  - Popular props
  - Relevant analysis angles
- [ ] One-click "Generate Research" button
- [ ] Template system for common analyses
- [ ] Card hover effects and animations

### Deliverables
- "Popular Bets" tab with auto-generated cards
- One-click report generation
- Pre-configured analysis templates

### Components to Build
- `PopularBets.tsx`
- `BetCard.tsx`
- `GameSelector.tsx`

### Dependencies
- Milestone 2 complete
- ESPN API integration

---

## 🔌 Milestone 6: Backend Integration
**Status**: 🔴 Not Started
**Priority**: Critical
**Time Estimate**: 6-8 hours

### Tasks
- [ ] Extend ESPN API client for detailed QB stats
- [ ] Build monthly aggregation logic (October vs others)
- [ ] Time slot categorization (parse game times)
- [ ] Home/away game filtering
- [ ] Calculate completion %, passer rating, etc.
- [ ] Create `/api/v1/analytics/qb-trends` endpoint
- [ ] Create `/api/v1/reports/generate` endpoint
- [ ] Add request validation (Pydantic models)
- [ ] Implement basic caching (in-memory)
- [ ] Error handling and logging

### Deliverables
- Working analytics API endpoints
- Fast response times (< 2 seconds)
- Accurate stat calculations

### Files to Create/Modify
- `apps/api/analytics/qb_analysis.py` (NEW)
- `apps/api/data_sources/fetchers.py` (MODIFY)
- `apps/api/main.py` (MODIFY)
- `packages/types/src/index.ts` (MODIFY)

### Dependencies
- ESPN API access confirmed
- Data models defined

---

## 📊 Milestone 7: Report Generation & Display
**Status**: 🔴 Not Started
**Priority**: Critical
**Time Estimate**: 5-6 hours

### Tasks
- [ ] Design report template layout
- [ ] Build chart components (bar charts, line charts)
- [ ] Integrate Recharts with black/orange theme
- [ ] Data table components for stats
- [ ] "Key Insights" section (bullet points)
- [ ] Recommendation badge (Favorable/Neutral/Unfavorable)
- [ ] Export to PNG functionality (`html2canvas`)
- [ ] Export to PDF functionality (`jsPDF`)
- [ ] Generate shareable link
- [ ] Loading states during generation
- [ ] Error states for failed generation

### Deliverables
- Beautiful, professional-looking reports
- Working export features
- Shareable report URLs

### Components to Build
- `GeneratedReport.tsx`
- `StatChart.tsx`
- `InsightsSection.tsx`
- `ExportButtons.tsx`
- `RecommendationBadge.tsx`

### Dependencies
- Milestone 4 complete (canvas built)
- Milestone 6 complete (API working)

---

## 🔗 Milestone 8: Report View Page
**Status**: 🔴 Not Started
**Priority**: Medium
**Time Estimate**: 2-3 hours

### Tasks
- [ ] Create `/app/reports/[id]/page.tsx` route
- [ ] Fetch report data by ID
- [ ] Display full report
- [ ] Add social sharing meta tags (OG, Twitter)
- [ ] Print-friendly CSS
- [ ] Mobile-responsive layout
- [ ] Copy link button
- [ ] Back to demo button

### Deliverables
- Shareable report page
- Good social sharing previews
- Works well on all devices

### Files to Create
- `app/reports/[id]/page.tsx` (NEW)
- `app/reports/[id]/layout.tsx` (NEW)

### Dependencies
- Milestone 7 complete

---

## 📱 Milestone 9: Polish & UX Improvements
**Status**: 🔴 Not Started
**Priority**: Medium
**Time Estimate**: 3-4 hours

### Tasks
- [ ] Add onboarding tooltips/tour
- [ ] Keyboard shortcuts for power users
- [ ] Undo/redo functionality for canvas
- [ ] Improved error messages
- [ ] Success animations
- [ ] Loading skeletons
- [ ] Empty states with helpful hints
- [ ] Dark mode throughout (already done)
- [ ] Accessibility audit (ARIA labels, keyboard navigation)
- [ ] Performance optimization

### Deliverables
- Polished, production-ready UX
- Fast, smooth interactions
- Accessible to all users

### Dependencies
- Milestones 1-8 complete

---

## 🚀 Milestone 10: Deployment & Launch
**Status**: 🔴 Not Started
**Priority**: High
**Time Estimate**: 2-3 hours

### Tasks
- [ ] Set up production environment variables
- [ ] Deploy frontend to Vercel/Netlify
- [ ] Deploy backend to AWS/Fly.io
- [ ] Configure custom domain
- [ ] Set up analytics (PostHog/Mixpanel)
- [ ] Error tracking (Sentry)
- [ ] Performance monitoring
- [ ] Create demo video/GIF
- [ ] Write launch announcement
- [ ] Share on Twitter/Reddit

### Deliverables
- Live production app
- Monitoring and analytics set up
- Launch materials ready

### Dependencies
- All previous milestones complete

---

## Progress Tracking

### Sprint 1 (Week 1)
**Goal**: Foundation + Core UI
- Milestone 1: Bunny Logo ✅
- Milestone 2: Demo Page Foundation ✅
- Milestone 3: Parameter Palette ✅

### Sprint 2 (Week 2)
**Goal**: Interactions + Backend
- Milestone 4: Report Canvas ✅
- Milestone 5: Popular Bets ✅
- Milestone 6: Backend Integration ✅

### Sprint 3 (Week 3)
**Goal**: Reports + Polish
- Milestone 7: Report Generation ✅
- Milestone 8: Report View Page ✅
- Milestone 9: Polish & UX ✅

### Sprint 4 (Week 4)
**Goal**: Launch
- Milestone 10: Deployment ✅
- Beta testing
- Gather feedback
- Iterate

---

## Current Status

**Active Milestone**: Milestone 1 (Bunny Logo)
**Next Up**: Milestone 2 (Demo Page Foundation)
**Blocked**: None
**Overall Progress**: 0/10 milestones complete (0%)

---

## Notes

- Focus on MVP features first (QB analysis only)
- Expand to other sports/positions in Phase 2
- Keep the build/demo interface intuitive and fast
- Test with real user scenarios frequently
- Maintain the black/orange brand throughout

---

## Questions to Resolve

1. Should we allow users to save reports to their account?
2. Do we need user authentication for MVP?
3. What's the priority order for adding more sports beyond NFL?
4. Should we integrate with sportsbooks (DraftKings, FanDuel) for live odds?
