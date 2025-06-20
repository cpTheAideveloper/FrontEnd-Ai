# How to Write Prompts for AI Component Creation

This guide teaches you how to write clear, detailed prompts that help AI models create high-quality frontend components consistently.

## Essential Prompt Structure

### 1. Component Definition (Always Include)
```
Create a [COMPONENT_TYPE] component that [PRIMARY_FUNCTION]
```
**Examples:**
- "Create a **modal component** that **displays user profile information**"
- "Create a **button component** that **handles form submissions with loading states**"
- "Create a **navigation component** that **adapts to different screen sizes**"

### 2. Technical Specifications (Critical Details)

#### Framework & Technology
```
- Framework: [React/Vue/HTML/Angular]
- Styling: [Tailwind CSS/CSS Modules/Styled Components]
- File Structure: [Single file/Multiple files/Component library]
- Dependencies: [None/Specific libraries needed]
```

#### Responsive Requirements
```
- Mobile: [Specific mobile behavior]
- Tablet: [Tablet-specific adaptations] 
- Desktop: [Desktop layout requirements]
- Breakpoints: [Custom breakpoints if needed]
```

### 3. Visual Design Instructions

#### Color Scheme
```
- Primary colors: [Specific colors or "modern blue theme"]
- Background: [Light/dark/gradient/custom]
- Text colors: [Contrast requirements]
- State colors: [Hover, active, disabled states]
```

#### Layout & Spacing
```
- Size: [Dimensions - small/medium/large or specific px/rem]
- Padding: [Internal spacing requirements]
- Margins: [External spacing]
- Alignment: [Left/center/right/justified]
```

### 4. Functionality Requirements

#### Core Features
```
- Primary action: [What happens when user interacts]
- Secondary actions: [Additional functionality]
- States: [Loading, error, success, disabled]
- Validation: [Form validation, input constraints]
```

#### User Interactions
```
- Click/tap behavior: [Immediate response]
- Hover effects: [Desktop hover states]
- Keyboard navigation: [Tab, Enter, Escape handling]
- Touch gestures: [Swipe, pinch, long press]
```

## Prompt Templates by Component Type

### Button Component Template
```
Create a [SIZE] button component that [ACTION] with these specifications:

**Styling:**
- Colors: [Primary color] background with [text color] text
- Shape: [Rounded/square/pill-shaped]
- Size: [Height and padding specifications]

**States:**
- Default: [Normal appearance]
- Hover: [Hover effect - color change, scale, etc.]
- Active: [Click/press feedback]
- Loading: [Spinner or loading animation]
- Disabled: [Grayed out appearance]

**Functionality:**
- onClick: [What happens when clicked]
- Loading state: [Show spinner during async operations]
- Keyboard accessible: [Tab and Enter key support]

**Responsive:**
- Mobile: [Touch-friendly sizing - min 44px height]
- Desktop: [Hover effects and cursor pointer]
```

### Modal Component Template
```
Create a modal component that [PURPOSE] with these features:

**Layout:**
- Size: [Small/medium/large or specific dimensions]
- Position: [Center screen/top/bottom]
- Background: [Overlay color and opacity]

**Content Structure:**
- Header: [Title, close button placement]
- Body: [Content area specifications]
- Footer: [Action buttons layout]

**Behavior:**
- Open trigger: [How modal opens]
- Close methods: [X button, overlay click, escape key]
- Animation: [Fade in/slide in/scale in]

**Responsive:**
- Mobile: [Full screen or adapted size]
- Desktop: [Centered with max-width]
```

### Form Component Template
```
Create a form component for [FORM_PURPOSE] with these requirements:

**Fields:**
- [List each field with type and validation]
- Example: "Email field with email validation and error display"

**Layout:**
- Structure: [Single column/two column/grouped fields]
- Spacing: [Gap between fields]
- Labels: [Above/beside/floating labels]

**Validation:**
- Real-time: [Validate on blur/change]
- Error display: [How errors are shown]
- Success states: [Confirmation feedback]

**Submission:**
- Submit button: [Text, styling, loading state]
- Success handling: [What happens after submission]
- Error handling: [Network error display]
```

## Critical Details to Always Specify

### 1. Accessibility Requirements
```
- ARIA labels: [Specify needed labels]
- Keyboard navigation: [Tab order, shortcuts]
- Screen reader support: [Announcements needed]
- Color contrast: [WCAG AA/AAA compliance]
- Focus indicators: [Visible focus styles]
```

### 2. Performance Considerations
```
- Loading strategy: [Lazy loading, preloading]
- Animation performance: [60fps requirements]
- Bundle size: [Lightweight/minimal dependencies]
- Memory usage: [Cleanup requirements]
```

### 3. Browser Compatibility
```
- Target browsers: [Modern browsers/IE11+/specific versions]
- Fallbacks: [Graceful degradation requirements]
- Progressive enhancement: [Core functionality first]
```

## Sample Complete Prompt

```
Create a React notification toast component that displays success/error messages with these specifications:

**Component Requirements:**
- Framework: React with TypeScript
- Styling: Tailwind CSS
- File: Single component file with interfaces

**Visual Design:**
- Size: Auto-width, 4rem height minimum
- Colors: Green for success, red for error, blue for info
- Position: Top-right corner of screen, stack vertically
- Animation: Slide in from right, fade out after 5 seconds

**Functionality:**
- Types: Success, error, info, warning
- Auto-dismiss: 5 seconds (configurable)
- Manual dismiss: X button in top-right
- Queue system: Multiple toasts stack properly
- Click to dismiss: Entire toast clickable

**Props Interface:**
- message: string (required)
- type: 'success' | 'error' | 'info' | 'warning'
- duration: number (default 5000ms)
- onDismiss: callback function
- persistent: boolean (prevents auto-dismiss)

**Responsive:**
- Mobile: Full width minus 1rem margin
- Desktop: Max 24rem width, fixed position

**Accessibility:**
- ARIA live region for screen readers
- Keyboard dismissible (Escape key)
- Focus management for dismiss button
- High contrast mode support

**Animation:**
- Enter: Slide from right + fade in (300ms)
- Exit: Fade out + slide right (200ms)
- Smooth transitions using transform/opacity
```

## Common Mistakes to Avoid

### ❌ Vague Requests
- "Make a nice button"
- "Create a modal"
- "Build a form component"

### ✅ Specific Requests
- "Create a primary action button with loading state"
- "Build a confirmation modal with custom close behavior"
- "Design a multi-step form with validation"

### ❌ Missing Context
- No framework specified
- No responsive requirements
- No accessibility considerations

### ✅ Complete Context
- Clear technology stack
- Device-specific behaviors
- Accessibility requirements included

## Quick Checklist for Component Prompts

**Before writing your prompt, ensure you have:**
- [ ] Clear component purpose and functionality
- [ ] Specific framework and styling approach
- [ ] Responsive behavior for all screen sizes
- [ ] Color scheme and visual design requirements
- [ ] User interaction specifications
- [ ] Accessibility requirements
- [ ] Performance considerations
- [ ] Sample data or use cases

**The better your prompt, the better your component will be!**
