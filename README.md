# MatPlay — Material Discovery & Palette Composer Platform

MatPlay is a high-performance, visual-first material discovery engine designed for architects, interior designers, and material manufacturers. Built with a modern Next.js 14 frontend and a robust Spring Boot backend, MatPlay enables seamless exploration of architectural finishes, real-time product comparisons, interactive palette creation, and direct lead dispatch.

---

## 🏗 Tech Stack & Architecture

### **Frontend (Client & SSR)**
* **Framework:** Next.js 14 (App Router)
* **Language:** TypeScript
* **Styling & Components:** Tailwind CSS, Shadcn UI
* **Icons & Animation:** Lucide Icons, Framer Motion
* **Deployment:** Vercel

### **Backend (Microservices & APIs)**
* **Framework:** Spring Boot 3 (Java 21)
* **Search Engine:** Typesense (Sub-second typo-tolerant search)
* **Database:** PostgreSQL 16
* **Object Storage:** AWS S3 (High-res media, CAD swatches, PDFs)
* **Notifications:** AWS SES / SendGrid (Transactional lead mailing)
* **Deployment:** Render

---

## 🗺 Platform Pages & Routing Structure

MatPlay is structured across 16 core functional modules:

| Route Path | Page Module | Description |
| :--- | :--- | :--- |
| `/login`, `/register` | **Auth** | Unified onboarding for buyers, brand suppliers, and platform admins. |
| `/` | **Homepage** | Lifestyle-focused visual discovery guiding users into 5 core navigation tabs. |
| `/search` | **Search Hub** | Transitional discovery engine featuring visual and voice search capabilities. |
| `/categories/[category]` | **Category Landing** | High-level category intros featuring lifestyle imagery and subcategory guides. |
| `/categories/.../[sub]` | **Product Listing** | 3-column product grid (`#F5F5F5` card tiles) with filter/sort controls. |
| `/products/[productSlug]`| **Product Detail** | Deep-dive specification views, store locators (Google Maps), and RFQ triggers. |
| `/brands` | **Brand Directory** | Directory listing of verified manufacturers and material brands. |
| `/brands/[brandSlug]` | **Brand Profile** | Customizable brand storefronts featuring project showcases and key statistics. |
| `/brand-dashboard` | **Brand Management** | Vendor back-office for managing analytics, team roles, and subscriptions. |
| `/brand-dashboard/products`| **Catalog Manager** | CRUD workspace for managing catalog items, RFQ quotes, and sample requests. |
| `/rfq` | **Inquiry / RFQ** | Streamlined Request for Quote and physical sample dispatch workflow. |
| `/inspirations` | **Inspirations Feed**| Pinterest-style visual feed featuring interactive, pinned product hotspots. |
| `/explore` | **Editorial Hub** | Articles, house tours, magazines, long-form video, and industry case studies. |
| `/palette-composer` | **Palette Composer** | Interactive moodboard canvas for assembling saved materials into client palettes. |
| `/make-my-style` | **Make My Style** | AI-driven style generator providing architectural and interior style recommendations. |
| `/studio` | **The Studio** | Collaborative presentation space for designers, clients, and consultants. |

---

## 📂 Project Directory Layout

```text
matplay-frontend/
├── .vscode/                # Workspace extension settings
├── public/                 # Static branding and placeholders
├── src/
│   ├── app/                # Next.js 14 App Router (All 16 routes)
│   ├── components/         # Shadcn UI primitives, cards, layout, maps
│   ├── hooks/              # Custom React hooks (Palette state, voice search)
│   ├── lib/                # API clients (Render link) and NextAuth utilities
│   ├── styles/             # Global Tailwind directives
│   └── types/              # OpenAPI TypeScript interfaces
├── .env.development        # Local environment configs
├── .env.production         # Vercel production configs
└── vercel.json             # Rewrites and reverse proxy configurations
