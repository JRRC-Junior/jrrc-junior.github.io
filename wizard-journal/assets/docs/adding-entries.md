# The Arcane Chronicles - File Structure & Entry Management Guide

## 📁 Recommended GitHub Repository Structure

```
wizard-journal/
├── index.html                 # Main journal interface
├── README.md                  # Project documentation
├── entries/
│   ├── entries.json          # Master list of all entries
│   ├── entry-001.html        # Individual entry files
│   ├── entry-002.html
│   ├── entry-003.html
│   └── ...
├── assets/
│   ├── css/
│   │   └── journal.css       # Separated styles (optional)
│   ├── js/
│   │   └── journal.js        # Separated JavaScript (optional)
│   └── images/
│       └── backgrounds/      # Any custom images
└── docs/
    └── adding-entries.md     # This guide
```

## 📝 Adding New Journal Entries

### Method 1: Simple Addition (Recommended for GitHub Pages)

1. **Update the entries array** in `index.html` around line 500:
   ```javascript
   this.entries = [
       // ... existing entries ...
       {
           id: 6,  // Next sequential ID
           title: "Your New Entry Title",
           date: "Game Date (Real Date)",
           preview: "First 100-150 characters of your entry...",
           file: "entry-006.html"  // Optional for future expansion
       }
   ];
   ```

2. **Add the entry content** in the `getEntryContent()` function around line 650:
   ```javascript
   const contents = {
       // ... existing entries ...
       6: `
           <div class="journal-entry active">
               <div class="entry-header">
                   <h2 class="entry-title">Your Entry Title</h2>
                   <div class="entry-date">Game Date (Real Date)</div>
               </div>
               <div class="entry-content">
                   <!-- Your content here -->
               </div>
           </div>
       `
   };
   ```

### Method 2: Modular Files (Advanced - Requires Server/Build Process)

1. **Create `entries/entries.json`**:
   ```json
   {
       "entries": [
           {
               "id": 1,
               "title": "The Awakening of Power",
               "date": "Sixth Day of Springtide, Year 1126 (January 10, 2025)",
               "preview": "Upon our arrival in the outer territories of Drakkenheim...",
               "file": "entry-001.html",
               "tags": ["drakkenheim", "introduction", "gnolls"],
               "session": 1
           }
       ]
   }
   ```

2. **Create individual entry files** like `entries/entry-001.html`:
   ```html
   <div class="journal-entry active">
       <div class="entry-header">
           <h2 class="entry-title">The Awakening of Power</h2>
           <div class="entry-date">Sixth Day of Springtide, Year 1126 (January 10, 2025)</div>
       </div>
       <div class="entry-content">
           <!-- Your content here -->
       </div>
   </div>
   ```

## 🎨 Content Formatting Guidelines

### Basic Structure
```html
<div class="entry-content">
    <p>Regular paragraphs for most content.</p>
    
    <h3>Section Headers</h3>
    <p>Use h3 for major sections within entries.</p>
    
    <div class="spell-reference">
        <strong>Spell Notes:</strong> Use this for magical observations,
        combat notes, or important tactical information.
    </div>
    
    <p>Use <em>emphasis</em> for spell names and important terms.</p>
    <p>Use <strong>strong</strong> for creature names and locations.</p>
</div>
```

### Styling Elements
- **Spell Names**: `<em>Fireball</em>` (golden color)
- **Creature/Location Names**: `<strong>Lord of the Feast</strong>` (bright gold)
- **Magical Notes**: Wrap in `<div class="spell-reference">` for special styling
- **Regular Text**: Standard paragraphs with automatic spacing

## 🚀 GitHub Pages Deployment

1. **Enable GitHub Pages** in your repository settings
2. **Set source** to "Deploy from a branch" → "main" → "/ (root)"
3. **Custom Domain** (optional): Add your domain to settings
4. **Auto-deployment**: Every push to main automatically updates the site

## 🔧 Advanced Features & Improvements

### Easy Additions for Better UX

1. **Character Profiles Page**:
   - Add links to party member bios
   - Include character artwork
   - Track relationships and character development

2. **Interactive Map**:
   - Embed a Drakkenheim map with location markers
   - Link locations to relevant journal entries

3. **Timeline View**:
   - Chronological visualization of events
   - Filter by character arcs or story threads

4. **Search Enhancements**:
   - Tag-based filtering (combat, exploration, roleplay)
   - Date range filtering
   - Character-specific searches

5. **Reader Engagement**:
   - Comment system (using GitHub Discussions)
   - "Favorite entries" functionality
   - Reading progress tracking

### Performance Optimizations

1. **Lazy Loading**: Load entry content only when viewed
2. **Image Optimization**: Compress any artwork/maps
3. **Caching**: Implement service worker for offline reading
4. **Mobile Optimization**: Enhanced mobile reading experience

## 📱 Mobile Considerations

The current design is mobile-responsive, but consider:
- **Swipe Navigation**: Between entries on mobile
- **Reading Mode**: Distraction-free full-screen reading
- **Touch-Friendly**: Larger touch targets for navigation
- **Offline Reading**: Cache entries for offline access

## 🎭 Theming & Customization

### Color Schemes
- **Current**: Dark magical theme with gold accents
- **Alternatives**: 
  - Light parchment theme for daytime reading
  - High contrast for accessibility
  - Seasonal themes (winter/spring variants)

### Typography
- **Headers**: Cinzel (fantasy serif)
- **Body**: Crimson Text (readable serif)
- **Consider**: Adding a sans-serif option for dyslexic readers

## 📊 Analytics & Insights

Consider adding (privacy-respecting):
- **Reading Analytics**: Most popular entries, reading time
- **GitHub Stats**: Stars, forks, visitor counts
- **Engagement Metrics**: Which entries generate most discussion

## 🔒 Content Management

### Version Control Best Practices
- **Branch per Session**: Create branches for major story arcs
- **Commit Messages**: "Session X: Entry Title - Brief description"
- **Release Tags**: Tag major story milestones
- **Backup Strategy**: Regular backups of entries.json

### Content Guidelines
- **Consistency**: Maintain character voice throughout
- **Spoiler Handling**: Use collapsible sections for major reveals
- **Reader Context**: Include enough context for new readers
- **Pacing**: Balance detail with readability

## 🚀 Future Enhancements

1. **RSS Feed**: For regular readers to get updates
2. **Print Styles**: Clean printing for physical copies  
3. **Audio Integration**: Voice narration of entries
4. **Community Features**: Guest entries from other party members
5. **Campaign Tools**: Integration with D&D Beyond or Roll20

This structure provides both immediate usability and room for future expansion as your campaign grows!
