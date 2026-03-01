# Travel Creations by Di — Full Site Build

## Overview
Redesign of travelcreationsbydi.com — a Texas Hill Country travel agency run by Diane Mack. 
The homepage (index.html) is already built and serves as the design system. Match its style exactly for all other pages.

## Tech Stack
- Pure HTML + CSS (no JS frameworks)
- Google Fonts: Pacifico (headings) + Poppins (body)
- Colors: teal (#00b4d8), teal-dark (#0096b7), yellow (#f4a024), light-bg (#e8f8fc), dark-text (#1a2b3c)
- Forms: use https://formsubmit.co/dmack@lamacchiaje.com as the form action
- Responsive (mobile-friendly)
- All pages share the same nav and footer from index.html

## Pages to Build

### 1. about.html — About Us / Meet Diane
- Hero: large header image area with "About Us" overlay (use a travel group photo from Unsplash)
- "Meet Diane" section with photo placeholder (circle) and bio text:
  - Diane Mack, Owner & Sr Travel Creator
  - Email: dmack@lamacchiaje.com  
  - Two passions: lifelong Disney fan + planning/organizing vacations
  - Became a travel advisor 7 years ago
  - Books Disney, Universal Orlando, honeymoons, cruises, girl's getaways, family adventures, spring break
  - Treats each client like family, handles every detail
  - Available before, during, and after trips
- Link to Travel Leaders Network Profile (just use # as placeholder href)

### 2. disney.html — Disney Deals
- Header banner: "Disney Deals"
- Photo strip/collage of Disney parks (use Unsplash images of theme parks, castles, etc.)
- "2026 Packages" section with CTA
- Promotional section: Disney Resort hotel guests get water park admission on check-in day (lazy rivers, wave pools, water slides)
- Dining Plan comparison: two cards side by side
  - Quick Service Plan: 2 quick service meals, 1 snack, 1 refillable drink & souvenir mug per person per night
  - Disney Dining Plan: 1 table service meal, 1 quick service meal, 1 snack, 1 refillable drink & souvenir mug per person per night
- CTA buttons throughout
- Use card-based layout matching homepage style

### 3. cruising.html — Cruising
- Header: "Cruising"
- Article content comparing River vs Ocean cruises:
  - "Intimate Exploration vs. Grand Adventures" — river cruises dock in charming towns; ocean cruises are floating resorts
  - "Relaxed vs. Energetic Pace" — river cruises are relaxed with nightly sailing; ocean cruises mix sea days with port calls
  - Conclusion: choice depends on personal preferences
- Section: cruises offer something for everyone — couples, families, friend groups (dining, spa, entertainment, shore excursions, kids' clubs, all-inclusive)
- Photos: use Unsplash cruise/ocean images
- "Exclusive Group Pricing" section with two promo cards
- CTA: "Request your cruise quote today!" button linking to contact.html

### 4. universal.html — Universal Destinations & Experiences
- Header banner: "Universal Destinations & Experiences"
- Brief intro text about Universal Orlando, Islands of Adventure, Epic Universe
- Video embed placeholder (use a YouTube iframe or styled placeholder)
- CTA to contact for Universal vacation planning

### 5. reviews.html — Reviews / What Our Travelers Say
- Hero: "What Our Travelers Say" heading
- "Happy Customers are our Goal!" section with text about developing relationships, listening to dreams, one-on-one service
- Reviews grid: at least 6 review cards with stars, quote text, and author names (reuse 3 from homepage + add 3 more)
- CTA: "Ready to plan your dream vacation?"

### 6. blog.html — Let's Talk Travel Blog
- Header: "Let's Talk Travel Blog!"
- Blog post cards in a grid (3-4 placeholder posts) with title, date, excerpt, "Read More" link
- Each links to a blog post page (e.g. blog-post-1.html)

### 7. blog-post-1.html — Sample Blog Post
- Single blog post layout with title, date, author, body content (placeholder travel topic)
- "Back to Blog" link
- Bottom CTA: "Ready to plan your trip?"

### 8. gallery.html — Adventure Gallery
- Header: "Adventure Gallery"
- Intro text inviting clients to submit travel photos
- Photo grid (CSS grid, 3-4 columns) with Unsplash adventure images (rafting, skiing, horseback riding, snorkeling, etc.)
- Featured stories section: 2 cards with photo + story text
- CTA: "Share your adventure photos with us!"

### 9. contact.html — Contact Us
- Hero with "Let's Plan Your Adventure!" overlay
- Three action cards: Request a Quote, Where to Next?, Let's Chat!
- Full contact form: Name, Email, Phone, Destination dropdown, Travel dates, Group size, Budget range, Message
  - Form action: https://formsubmit.co/dmack@lamacchiaje.com
  - Hidden _subject field: "New Trip Request from Website"
  - Hidden _next: thank-you.html
- Contact info: 110 Hideaway Circle, Ingram TX 78025, dmack@lamacchiaje.com, (469) 248-6318
- Social links: Facebook (https://www.facebook.com/yourtravelcreator), Instagram (https://www.instagram.com/yourtravelcreator/)

### 10. thank-you.html — Thank You Page
- Simple confirmation: "Thanks! We'll be in touch soon."
- Link back to homepage

## Shared Styles
- Extract all CSS from index.html into a shared styles.css file
- Update index.html to link to styles.css instead of inline styles
- All new pages link to the same styles.css
- Add page-specific styles at the bottom of styles.css or inline if minimal
- Nav should highlight current page (add .active class)
- Mobile hamburger menu (CSS-only checkbox hack preferred)

## SEO
- Each page: unique <title> and <meta description>
- Semantic HTML (header, main, section, article, footer)
- Alt text on all images
- One h1 per page

## File Structure
```
├── index.html (ALREADY EXISTS — extract CSS to styles.css, link to it)
├── about.html
├── disney.html
├── cruising.html
├── universal.html
├── reviews.html
├── blog.html
├── blog-post-1.html
├── gallery.html
├── contact.html
├── thank-you.html
├── styles.css
└── screenshots/ (reference only — original site screenshots)
```

## Reference
The screenshots/ directory has full-page screenshots of the original site. Use these for content reference. Match actual text where visible, but apply the new clean design from index.html.
