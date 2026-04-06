# CylindShare - Crisis LPG Cylinder Sharing Platform

CylindShare is a full-stack web platform designed for crisis situations in India, enabling verified users to lend and borrow LPG cylinders safely within their community.

## 🚀 Features

### 🎨 Dual Theme System
- **Light Mode**: Soft pastel colors (pastel pink, blue, mint, lavender, cream whites)
- **Dark Mode**: Deep jewel tones (navy, charcoal, slate, emerald, purple-black)
- Smooth 300ms transition animations
- Glassmorphism effects in dark mode

### 🔐 Authentication & Verification
- Multi-step registration with Aadhaar verification
- Selfie capture for identity verification
- Email/password login with Supabase Auth
- Verification status tracking

### 🗺️ Interactive Map
- Real-time cylinder availability visualization
- Red markers for lenders, blue markers for borrowers
- Clickable popups with cylinder details and chat option
- Location-based filtering with distance radius
- Voice search integration
- Live crisis statistics bar
- Crisis news feed

### 📋 Listings Page
- OLX-style responsive grid (3 cols desktop, 2 tablet, 1 mobile)
- Company-specific color coding (HP=red, Indane=blue, Bharatgas=green)
- Advanced filters: company, weight, type, verified users, availability
- Sort options: newest, nearest, free first
- Voice search capability
- Verified user badges
- Direct chat integration

### 💬 Real-Time Chat
- Conversation list sidebar
- Real-time messaging (polling every 3 seconds)
- Safety reminders and warnings
- Cylinder details in chat header
- Message timestamp display
- Auto-scroll to latest messages

### 📊 Analytics Dashboard
- Crisis Severity Index (0-100 gauge)
- Total cylinders listed (with sparkline)
- Company breakdown (donut chart)
- Top 5 cities by activity (bar chart)
- Listings over time (line chart - last 7 days)
- Verified vs unverified users (pie chart)
- Average lending duration gauge
- Recent transactions table with status badges

### 👤 User Profile
- Profile header with verification status
- **My Listings Tab**: Grid of user's cylinder listings with add listing modal
- **My Borrowings Tab**: Track borrowed cylinders
- **Transaction History Tab**: Complete transaction log with safety checklist status
- **Settings Tab**: Account management
- Safety checklist modal (6 mandatory checks before publishing)
- Auto-location detection

### 🛡️ Safety Features
- Mandatory safety checklists before transactions
- Safety precautions accordion on landing page
- Digital agreements and documentation tracking
- Condition tags and inspection guidelines
- Emergency helpline numbers in footer

### 🎤 Voice Input
- Web Speech API integration
- Microphone button on all search bars
- Real-time transcript to search query
- Visual feedback during listening

## 🛠️ Tech Stack

### Frontend
- **React 18** with TypeScript
- **React Router 7** (Data mode)
- **Tailwind CSS v4** for styling
- **Shadcn/ui** components
- **Recharts** for data visualization
- **Leaflet** and **React Leaflet** for maps
- **Motion** for animations
- **Sonner** for toast notifications

### Backend
- **Supabase** for:
  - Authentication
  - Database (using KV store)
  - Edge Functions (Hono server)
- **Deno** runtime for edge functions

### Database Schema
Using Supabase KV Store for:
- **users**: id, name, phone, email, aadhaar_hash, selfie_url, verified_status, role, location_lat, location_lng, created_at
- **cylinders**: id, owner_id, company, weight_kg, condition, images[], is_available, listing_type, price_or_free, location_lat, location_lng, address, created_at
- **transactions**: id, cylinder_id, lender_id, borrower_id, status, start_date, end_date, safety_checklist_signed
- **messages**: id, conversation_id, sender_id, receiver_id, content, timestamp
- **conversations**: id, buyer_id, seller_id, cylinder_id, created_at
- **reports**: id, reporter_id, reported_user_id, reason, created_at

## 📱 Pages

1. **Landing (/)**: Hero section, features, how it works, safety precautions, live stats, footer
2. **Register (/register)**: 3-step registration with verification
3. **Login (/login)**: Email/password authentication
4. **Map (/map)**: Interactive map with filters, stats bar, news feed
5. **Listings (/listings)**: Grid view with filters, sorting, voice search
6. **Chat (/chat)**: Real-time messaging with safety warnings
7. **Analytics (/analytics)**: Dashboard with charts and insights
8. **Profile (/profile)**: User management with tabs for listings, borrowings, transactions, settings

## 🔑 Key Features

### Responsive Design
- Mobile-first approach
- Breakpoints: mobile (1 col), tablet (2 cols), desktop (3 cols)
- Collapsible mobile menu
- Bottom sheet filters on mobile

### Accessibility
- ARIA labels on all interactive elements
- High contrast ratios
- Keyboard navigation support
- Screen reader friendly

### Performance
- Loading skeletons for all data-fetched content
- Optimistic UI updates
- Efficient polling for real-time features
- Lazy loading components

## 🚦 Getting Started

1. The platform is already configured with Supabase
2. Register a new account at `/register`
3. Complete the 3-step verification process
4. Browse cylinders on the map or listings page
5. Chat with lenders/borrowers
6. List your own cylinders from your profile

## 🔒 Security

- Aadhaar numbers are hashed before storage
- Supabase Row Level Security
- Service role key never exposed to frontend
- Token-based authentication
- Secure password handling

## 📞 Emergency Contacts

- LPG Emergency: 1906
- Fire Emergency: 101
- Police: 100

## 🎯 Crisis Focus

This platform is specifically designed for crisis situations where:
- Gas agencies are on strike
- Supply disruptions occur
- Emergency situations require community support
- Verified neighbors need to share resources safely

---

**Built for India's Crisis Response** 🇮🇳
