# World Payment Map

## What
An interactive world map that shows the dominant payment methods used by people in each country/region. Covers 60+ countries with details on payment apps, adoption rates, and notable facts.

## Why
Visual reference for understanding the global payments landscape — useful for AllScale's research and content.

## Plan

### Tech Stack
- **Framework:** Next.js (App Router) — works natively with Vercel
- **Map Library:** react-simple-maps (D3-based, lightweight, supports TopoJSON)
- **Styling:** Tailwind CSS
- **Data:** Static JSON embedded in the app (60+ countries)

### Features
1. Interactive world map with color-coded countries by digital payment adoption %
2. Hover/click on a country to see:
   - Country name & flag
   - Top 2-3 payment methods
   - Digital payment adoption %
   - Notable fact
3. Color legend (gradient from low to high adoption)
4. Responsive design (works on mobile)
5. Search/filter by payment method or region

### Implementation Steps
1. ✅ Create project plan
2. Scaffold Next.js app with Tailwind
3. Add payment data JSON (60+ countries)
4. Build map component with react-simple-maps
5. Add country detail panel (hover/click)
6. Add color legend and region filters
7. Style and polish
8. Create GitHub repo
9. Deploy to Vercel

### Acceptance Criteria
- [ ] Map renders all 60+ countries with correct data
- [ ] Hover shows payment method info
- [ ] Color-coded by adoption rate
- [ ] Deployed and accessible on Vercel
- [ ] GitHub repo created and pushed
