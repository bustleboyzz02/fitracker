# FitTrackr Design Guidelines

## Design Approach
**Reference-Based Approach**: Modern fitness app aesthetic inspired by contemporary wellness platforms with glassmorphism UI and dynamic media backgrounds. The design emphasizes visual immersion through full-screen background videos/images that change per section while maintaining clarity through layered transparency effects.

## Core Design Elements

### A. Typography
- **Font Stack**: Inter, Poppins as primary system fonts
- **Heading Sizes**: 
  - H1 (Brand): 1.05rem (mobile: 1rem)
  - H2 (Section titles): 1.9rem
  - H3 (Card headings): Standard weight
- **Body Text**: Lead paragraphs at 1.6 line-height for readability
- **Weights**: Regular (400) for body, Semi-bold (600) for navigation, Extra-bold (800) for buttons, Black (900) for emphasis

### B. Color Palette
- **Primary Orange**: #ff8c42 (brand color)
- **Secondary Orange**: #ff9d5a (gradient accent)
- **Background**: #070707 (near-black)
- **Text**: #f3f3f3 (off-white muted)
- **Glass Effects**: rgba(255,140,66,0.06) for subtle tints

### C. Layout System
**Spacing Scale**: Use 8px, 10px, 12px, 14px, 16px, 18px, 28px, 48px for consistent rhythm
- **Max-width Container**: 1200px for main content
- **Grid Patterns**: Two-column (1fr + 420px) on desktop, single column on mobile (<980px)
- **Section Padding**: 48px vertical, 28px horizontal on desktop; 6px on mobile
- **Card Spacing**: 16px internal padding, 12px gaps in grids

### D. Component Library

**Glassmorphism Cards**:
- Background: rgba(255,255,255,0.03) with 1px border rgba(255,140,66,0.04)
- Border-radius: 12px for cards, 10px for smaller elements
- Backdrop-filter: blur(6px) for header
- Box-shadow: 0 12px 30px rgba(0,0,0,0.5)

**Buttons**:
- Primary: Linear gradient (90deg, #ff8c42 to #ff9d5a), black text, 10px padding, 10px radius
- Ghost: Transparent background, 1px border rgba(255,255,255,0.06), muted text
- All buttons: 800 font-weight

**Forms**:
- Input fields: rgba(255,255,255,0.04) background, 8px radius, 10px padding
- Max-width: 360px for form containers
- 8px gap between form elements

**Navigation**:
- Fixed header positioned 12px from top, glassmorphic background
- Logo: 44x44px rounded square with gradient background
- Nav links: 8px padding, 8px radius, hover transforms translateY(-3px)

**Package Cards**:
- Grid: Auto-fit minmax(220px, 1fr)
- Background: Linear gradient (180deg, rgba(0,0,0,0.45) to 0.55)
- Price typography: 1.2rem, 900 weight, orange-2 color

### E. Background Media System
- **Full-screen layered backgrounds**: Fixed position videos/images at z-index -4/-5
- **Adaptive content**: Desktop video, mobile video, fallback images, and animated gradient
- **Per-section media**: Each page section specifies its own background media via data attributes
- **Fallback strategy**: Video → Image → Animated gradient

### F. Page Transitions
- **Slide animations**: translateX transitions with cubic-bezier(.2,.9,.2,1) easing over 0.6s
- **Hidden states**: -120% left/right with opacity 0
- **Active state**: translateX(0) with opacity 1, z-index 5
- **Performance**: will-change: transform, opacity

### G. Responsive Breakpoints
- **Mobile**: <720px - Adjusted header positioning, reduced font sizes
- **Tablet**: <980px - Single column layouts
- **Desktop**: >980px - Two-column grid layouts

## Images
**Background Media Strategy**: Each section uses full-screen background videos (desktop/mobile variants) with static image fallbacks:
- Home: Gym workout scenes
- Login: Kettlebell workout footage  
- Register: Sunrise workout ambiance
- Health/Diet: Fresh vegetables and meal prep
- Contact: Community fitness activities

**No discrete hero images** - instead, immersive full-viewport backgrounds create context for each section's content while maintaining foreground clarity through glassmorphic overlays.

## Key Design Principles
1. **Layered Transparency**: Content floats above dynamic backgrounds using glass effects
2. **Consistent Radius**: 12px for major cards, 10px for buttons/smaller elements, 8px for inputs
3. **Orange Accent System**: Used for brand identity, CTAs, headings, and interactive states
4. **Spatial Rhythm**: Generous whitespace with consistent 12px/16px/28px gaps
5. **Minimal Animation**: Subtle hover transforms (-3px translateY), page slide transitions only