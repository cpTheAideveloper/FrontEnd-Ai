# Instagram-Style Story Carousel Component Prompt

Create a complete Instagram-style story carousel component in a single HTML file that allows users to click circular profile pictures to view stories (images/videos). Follow these exact specifications:

## Design System & Styling Requirements

### Color Palette (Tailwind CSS)
- **Primary Background**: `bg-gray-900` (dark theme)
- **Secondary Background**: `bg-gray-800`
- **Accent Colors**: 
  - Story ring (unviewed): `from-purple-500 via-pink-500 to-red-500` (gradient)
  - Story ring (viewed): `border-gray-400`
  - Text Primary: `text-white`
  - Text Secondary: `text-gray-300`
- **Interactive States**:
  - Hover: `hover:scale-105`
  - Active: `active:scale-95`
  - Focus: `focus:ring-2 focus:ring-purple-500`

### Spacing & Layout (Mobile-First)
- **Container**: `max-w-sm mx-auto` (mobile), `md:max-w-4xl` (desktop)
- **Story Circles**: `w-16 h-16` (mobile), `md:w-20 md:h-20` (desktop)
- **Gaps**: `gap-4` (mobile), `md:gap-6` (desktop)
- **Padding**: `p-4` (mobile), `md:p-6` (desktop)
- **Margins**: `mb-4` between sections

### Typography
- **Username**: `text-sm font-medium` (mobile), `md:text-base` (desktop)
- **Story Viewer Title**: `text-lg font-bold`
- **Timestamps**: `text-xs text-gray-400`

## Component Structure Requirements

Build these components in a single HTML file:

### 1. StoryCarousel (Main Container)
- Horizontal scrollable list of story circles
- Smooth scroll behavior: `scroll-smooth`
- Hide scrollbar: `scrollbar-hide` or custom CSS

### 2. StoryCircle (Individual Story Preview)
- Circular profile image with gradient border for unviewed stories
- Username below the circle
- Click handler to open story viewer
- Viewed/unviewed state management

### 3. StoryViewer (Full-Screen Modal)
- Full-screen overlay: `fixed inset-0 bg-black bg-opacity-90`
- Story content (image/video) centered and responsive
- Progress bars at the top showing story progression
- Navigation: tap left/right or swipe to navigate
- Close button (X) in top-right corner
- Auto-advance timer for stories (5 seconds per story)

### 4. ProgressBar (Story Progress Indicator)
- Multiple segments representing each story in the set
- Active segment fills with white, completed segments are white, upcoming are gray
- Smooth animation: `transition-all duration-300`

## Functionality Requirements

### Core Features
1. **Story Data Structure**: Each user should have multiple stories with:
   ```javascript
   {
     id: 'user1',
     username: 'john_doe',
     profileImage: 'url',
     stories: [
       { id: 1, type: 'image', url: 'url', timestamp: 'time' },
       { id: 2, type: 'video', url: 'url', timestamp: 'time' }
     ],
     viewed: false
   }
   ```

2. **Interactive Behaviors**:
   - Click story circle → opens story viewer
   - Tap left half → previous story
   - Tap right half → next story  
   - Auto-advance every 5 seconds
   - Mark stories as viewed
   - Smooth transitions between stories

3. **Mobile Gestures** (optional but preferred):
   - Swipe left/right for navigation
   - Touch and hold to pause auto-advance

### State Management
- Track current user and story index
- Manage viewed/unviewed states
- Handle auto-advance timers
- Responsive image/video loading

## Technical Implementation

### HTML Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Instagram Story Carousel</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-900 text-white">
    <!-- Component implementation here -->
</body>
</html>
```

### JavaScript Requirements
- Use vanilla JavaScript (no external libraries)
- Implement proper event listeners
- Handle touch events for mobile
- Memory management for timers
- Error handling for media loading

### CSS Customizations
Include custom CSS for:
- Gradient borders for story circles
- Smooth scrolling horizontal carousel
- Hide scrollbars
- Media queries for responsive design
- Animation keyframes

## Sample Data
Provide at least 5-6 sample users with 2-4 stories each, mixing images and videos. Use placeholder URLs or sample content.

## Performance Considerations
- Lazy load story content
- Preload next/previous stories
- Optimize images for mobile
- Smooth 60fps animations
- Minimal DOM manipulation

## Accessibility
- Proper ARIA labels
- Keyboard navigation support
- Focus management
- Screen reader compatibility

Create a fully functional, production-ready component that replicates the Instagram story experience with smooth animations and responsive design.
