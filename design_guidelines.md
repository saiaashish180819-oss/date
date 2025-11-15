# Design Guidelines: Enhanced Interactive "Ask Out" Page

## Design Approach

**Selected Approach:** Experience-Focused Custom Design
- **Inspiration:** Blend of modern dating apps (Tinder, Bumble) with playful game UI aesthetics
- **Core Principle:** Create an emotionally engaging, delightful micro-experience that feels special and personal
- **Key Focus:** Smooth animations, tactile interactions, and celebratory feedback

## Layout System

**Viewport Strategy:**
- Single centered card design (full viewport height justified)
- Card max-width: 480px on desktop, 90% on mobile
- Vertical centering with safe padding for mobile keyboards

**Spacing Primitives:**
- Use Tailwind units: 4, 6, 8, 12, 16, 20 (p-4, gap-6, mt-8, etc.)
- Card internal padding: p-8 on desktop, p-6 on mobile
- Element spacing: space-y-6 for vertical stacking within card

## Typography

**Hierarchy:**
- Heading (question): text-2xl md:text-3xl, font-bold, leading-tight
- Input placeholder: text-base, font-normal
- Button text: text-base, font-semibold, tracking-wide
- Popup message: text-xl md:text-2xl, font-bold

**Font Selection:**
- Primary: System font stack or Google Fonts - "Inter" for clean modern look
- Alternative: "Poppins" for more playful personality

## Component Library

### Card Container
- Glassmorphic treatment with backdrop blur
- Rounded corners: rounded-2xl
- Subtle border and shadow for depth
- Smooth gradient border on hover/interaction states

### Input Field
- Full width with rounded-xl
- Padding: px-4 py-3
- Smooth focus state with ring effect
- Floating label or animated placeholder

### Button System

**YES Button:**
- Prominent primary button with gradient treatment
- Padding: px-8 py-3
- Rounded-xl
- Scale transform on hover (scale-105)
- Smooth transition on all states
- Glow effect on hover

**NO Button:**
- Secondary styling (subtle, less prominent)
- Same padding and rounding as YES
- Dodging behavior after first click
- Smooth position transitions (transition-transform duration-200)

### Popup/Modal
- Fixed centered positioning
- Backdrop blur overlay
- Scale-in animation (0.8 to 1.0)
- Fade in/out transitions
- Auto-dismiss after 3-4 seconds
- Larger padding for impact: p-8 md:p-12

## Background & Ambiance

**Background Treatment:**
- Animated gradient or subtle particle system
- Floating heart or sparkle elements (3-5 particles max)
- Particle size: 20-40px, slow drift animation
- Low opacity to avoid distraction (0.1-0.3)

**Background Animation:**
- Gentle gradient shift over 10-15 seconds
- Subtle radial glow emanating from card

## Interaction & Animation Guidelines

**Critical Animations:**

1. **Page Load:**
   - Card: fade-in + scale-up (0.95 to 1.0, duration-500)
   - Content: staggered fade-in (delay between elements: 100ms)

2. **NO Button Dodge:**
   - After first click: enable mousemove tracking
   - Transform position on hover (translate-x/y random values)
   - Smooth transform transition: duration-200 ease-out
   - Add subtle card glow when dodging begins

3. **YES Button Click:**
   - Button: scale-down momentarily then back
   - Confetti/celebration effect (brief, 2-3 seconds)
   - Popup appears with scale + fade animation

4. **Input Focus:**
   - Ring effect with smooth transition
   - Slight scale (1.02) or glow on focus

**Animation Constraints:**
- Use CSS transforms (not position changes)
- Keep durations under 500ms for UI feedback
- Celebration effects: 2-3 seconds max, then fade out
- All animations: ease-out or ease-in-out curves

## Responsive Behavior

**Mobile Adjustments:**
- Card: reduce padding from p-8 to p-6
- Typography: scale down by one size step
- Button row: remain horizontal (flex-row) if space permits
- Ensure NO button can dodge within viewport bounds
- Popup: reduce padding and font size appropriately

**Touch Interactions:**
- NO button: on mobile, dodge on tap (not mousemove)
- Ensure tap targets meet 44px minimum

## Special Effects (Use Decisively)

**Celebration on YES:**
- Confetti particles (10-15 pieces)
- Launch from center, spread outward
- Rainbow or romantic palette
- Fade out after 2 seconds
- OR Heart burst animation as alternative

**Card Glow State:**
- Applied when NO dodging is activated
- Subtle outer glow pulse
- Indicates "game mode" is active

## Accessibility Notes

- Maintain focus indicators on all interactive elements
- Ensure sufficient contrast for text readability
- Popup message should be announced to screen readers
- Keyboard navigation: Tab through YES/NO buttons
- Space/Enter to activate buttons

## Technical Implementation Notes

- Use CSS transforms for all animations (better performance)
- Particle effects: CSS-only or minimal canvas
- Keep DOM manipulation minimal
- Use requestAnimationFrame for smooth dodging behavior
- Prevent button spam with debouncing

---

**Success Criteria:** The final design should feel like a polished, delightful gift - modern, playful, and emotionally resonant. Every interaction should spark joy and anticipation.