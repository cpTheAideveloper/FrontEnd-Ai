# Adaptive Navbar Component Prompt

Create a responsive navigation component that adapts to different screen sizes with distinct layouts: mobile bottom bar, tablet sidebar, and desktop top navbar. Build everything in a single HTML file following mobile-first principles.

## Design System & Color Palette

### Color Scheme (Minimal White/Black)
- **Primary Background**: `bg-white` (light mode) / `bg-black` (dark mode)
- **Secondary Background**: `bg-gray-50` / `bg-gray-900`
- **Text Colors**:
  - Primary: `text-black` / `text-white`
  - Secondary: `text-gray-600` / `text-gray-400`
  - Muted: `text-gray-400` / `text-gray-600`
- **Borders**: `border-gray-200` / `border-gray-800`
- **Active States**: `bg-black text-white` / `bg-white text-black`
- **Hover States**: `bg-gray-100` / `bg-gray-800`

### Spacing & Dimensions (Mobile-First)
- **Mobile Bottom Bar**: `h-16` height, `p-2` padding
- **Tablet Sidebar**: `w-16` width (collapsed), `w-64` (expanded), `h-screen`
- **Desktop Top Bar**: `h-14` height, `px-6` horizontal padding
- **Icon Sizes**: `w-6 h-6` (mobile), `w-5 h-5` (desktop)
- **Gaps**: `gap-1` (mobile), `gap-4` (tablet), `gap-6` (desktop)

## Responsive Breakpoints & Layouts

### Mobile (default - 0px to 767px)
**Bottom Navigation Bar**
- Position: `fixed bottom-0 left-0 right-0 z-50`
- Layout: Horizontal flex with 4-5 main navigation items
- Background: `bg-white border-t border-gray-200`
- Items: Icon + label, center-aligned
- Active item: Different background color and bold text

### Tablet (768px to 1023px)
**Left Sidebar Navigation**
- Position: `fixed left-0 top-0 h-screen z-40`
- Default: Collapsed (`w-16`) with icons only
- Hover/Click: Expand to `w-64` with labels
- Background: `bg-white border-r border-gray-200`
- Items: Icon + expandable label
- Smooth transition: `transition-all duration-300 ease-in-out`

### Desktop (1024px+)
**Top Navigation Bar**
- Position: `fixed top-0 left-0 right-0 z-50`
- Layout: Horizontal with logo left, nav center, actions right
- Background: `bg-white border-b border-gray-200`
- Items: Text-based with optional icons
- Dropdown menus for complex navigation

## Animation Requirements

### Hover Effects
- **Mobile**: `active:scale-95` (touch feedback)
- **Tablet**: `hover:bg-gray-100 hover:scale-105`
- **Desktop**: `hover:bg-gray-100 hover:text-black`
- **Transitions**: `transition-all duration-200 ease-in-out`

### Interactive Animations
- **Active State**: Smooth color transition with scale effect
- **Sidebar Expansion**: `transform translate-x-0` with width animation
- **Menu Dropdowns**: `opacity-0 scale-95` to `opacity-100 scale-100`
- **Loading States**: Subtle pulse effect on nav items

## Component Structure

### 1. NavigationContainer (Main Wrapper)
- Responsive wrapper that shows/hides different nav layouts
- Handles screen size detection
- Manages active states across layouts

### 2. MobileBottomBar
- Fixed bottom navigation
- Icon + text layout
- Touch-friendly tap targets (`min-h-[44px]`)
- Safe area handling for iOS devices

### 3. TabletSidebar
- Collapsible sidebar
- Hover expansion functionality
- Icon-first design with hidden labels
- Smooth width transitions

### 4. DesktopTopbar
- Traditional horizontal navigation
- Logo, navigation, and action areas
- Dropdown menu support
- Search integration (optional)

### 5. NavigationItem (Reusable)
- Flexible component for all layouts
- Icon + label with conditional rendering
- Active/inactive states
- Accessibility attributes

## Navigation Structure

### Primary Navigation Items
Include these 5 core navigation items:
1. **Home** - House icon, main dashboard/landing
2. **Explore** - Search/compass icon, discovery page
3. **Create** - Plus icon, content creation
4. **Messages** - Chat icon, communication
5. **Profile** - User icon, account settings

### Secondary Actions (Desktop/Tablet)
- **Search Bar** - Expandable search input
- **Notifications** - Bell icon with badge counter
- **Settings** - Gear icon for preferences
- **Theme Toggle** - Sun/moon icon for light/dark mode

## Technical Implementation

### HTML Structure Template
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adaptive Navigation</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest/dist/umd/lucide.js"></script>
</head>
<body class="bg-gray-50">
    <!-- Mobile Bottom Bar (default) -->
    <!-- Tablet Sidebar (md:) -->
    <!-- Desktop Top Bar (lg:) -->
</body>
</html>
```

### JavaScript Functionality
- **Active state management** across all layouts
- **Sidebar toggle** for tablet view
- **Dropdown menus** for desktop
- **Touch gesture** support for mobile
- **Keyboard navigation** support
- **Theme switching** functionality

### CSS Custom Properties
```css
:root {
  --nav-height-mobile: 4rem;
  --nav-width-tablet: 4rem;
  --nav-width-tablet-expanded: 16rem;
  --nav-height-desktop: 3.5rem;
  --transition-speed: 300ms;
}
```

## Responsive Display Classes

### Visibility Control
- Mobile: `block md:hidden` (bottom bar only)
- Tablet: `hidden md:block lg:hidden` (sidebar only)
- Desktop: `hidden lg:block` (top bar only)

### Layout Adjustments
- **Mobile**: Account for bottom nav with `pb-16` on main content
- **Tablet**: Account for sidebar with `md:ml-16` on main content
- **Desktop**: Account for top nav with `lg:pt-14` on main content

## Accessibility Requirements

### ARIA Labels
- Navigation landmark: `role="navigation"`
- Current page: `aria-current="page"`
- Expandable menus: `aria-expanded="true/false"`
- Screen reader labels: `aria-label` for icon-only buttons

### Keyboard Navigation
- Tab order management
- Enter/Space key activation
- Escape key for closing menus
- Arrow key navigation in dropdowns

### Focus Management
- Visible focus indicators: `focus:ring-2 focus:ring-black`
- Focus trapping in expanded menus
- Skip links for screen readers

## Sample Data Structure
```javascript
const navigationItems = [
  { id: 'home', label: 'Home', icon: 'Home', href: '/' },
  { id: 'explore', label: 'Explore', icon: 'Search', href: '/explore' },
  { id: 'create', label: 'Create', icon: 'Plus', href: '/create' },
  { id: 'messages', label: 'Messages', icon: 'MessageCircle', href: '/messages' },
  { id: 'profile', label: 'Profile', icon: 'User', href: '/profile' }
];
```

## Performance Considerations
- **Minimal JavaScript**: Use CSS transforms for animations
- **Touch optimization**: 44px minimum touch targets
- **Preload icons**: Use icon fonts or SVG sprites
- **Smooth animations**: Use `transform` and `opacity` for 60fps
- **Lazy loading**: Load dropdown content on demand

Create a production-ready, fully accessible navigation system that provides optimal user experience across all device types with smooth animations and intuitive interactions.
