# ISM ENGINEERING — Official Website & Booking Platform

Production-ready, professional website and service dispatch system for **ISM ENGINEERING**, a real local air conditioning and home-appliance repair business based in Tirupur, Tamil Nadu, India.

---

## 🏢 Business Information
- **Business Name**: ISM ENGINEERING
- **Address**: 166, VGV GARDEN, THIRUMURUGAN POONDI, TIRUPUR, Tamil Nadu, India - 641652
- **Direct Phone**: [8056494838](tel:+918056494838)
- **WhatsApp**: [+91 80564 94838](https://wa.me/918056494838)
- **Working Hours**: Monday – Sunday: 8:00 AM – 9:00 PM
- **Service Area**: Doorstep visits across Thirumurugan Poondi, Avinashi Road, 15 Velampalayam, Kumar Nagar, Rayapuram, Gandhi Nagar, PN Road, Pushpa Theater Area, Kangeyam Road, Palladam Road, Chettipalayam, and greater Tirupur.

---

## 🎨 Design & Brand Identity
- **Agency-Grade Aesthetic**: Custom engineered look with deep navy blue (`#070d1d`, `#0b132b`, `#0f172a`), crisp white, and cyan (`#00b4d8`, `#38bdf8`) palette.
- **Custom Logo**: Vector brand mark combining an air conditioning snowflake crystal, electrical energy spark, and mechanical gear boundary.
- **Typography**: Clean, readable grotesque sans-serif (*Plus Jakarta Sans*) with monospace numerals for phone numbers and ticket references.
- **Realistic Photography**: Authentic technician photos showing indoor coil maintenance, pressure gauges, refrigerator cooling checks, and switchboard repairs.
- **Truthful Content**: Zero fake certifications, zero invented testimonials, zero fake statistics, and zero fabricated awards.

---

## 🚀 Key Features

### 1. Navigation & Floating Actions
- Top notification bar displaying real working hours, local Tirupur coverage, and one-click copy phone number with visual feedback.
- Sticky responsive navbar with clear links, click-to-call (`tel:+918056494838`), and instant WhatsApp chat.
- Mobile bottom action bar with **"Call 8056494838"** and **"Book Service"** for mobile users.
- Pulsing floating WhatsApp button on desktop and mobile.

### 2. Editable Service Categories
Individual service cards with checklist points, common warning signs, and direct booking actions for:
1. **Air Conditioner Repair & Servicing**
2. **AC Installation & Uninstallation**
3. **AC Cooling & Water Leakage Problems**
4. **Refrigerator Repair & Cooling Problems**
5. **Washing Machine Servicing**
6. **Electrical Switch & Minor Electrical Repair**
7. **Other Home-Appliance Repair Requests**
> **Editable by Owner**: Business owners can add new service categories, edit titles/descriptions, or remove services in real-time from the built-in Owner Portal.

### 3. Customer Service Booking Form
- **Fields**: Customer name, 10-digit Indian mobile number validation, address/area in Tirupur (with quick area chips), appliance type dropdown, dynamic problem category dropdown, detailed problem textarea, preferred date picker, and preferred time window.
- **Photo Upload**: Supports `.jpg`, `.jpeg`, `.png`, and `.webp` images up to 5MB each (up to 3 photos) with instant thumbnail previews, file size indicators, and removal buttons.
- **Transparent Booking Summary**: Reference ID generation (`ISM-2026-XXXX`), clear summary modal, and explicit photo attachment instructions explaining web browser security constraints for WhatsApp.
- **WhatsApp Integration**: Generates a prefilled, structured, properly URL-encoded WhatsApp message to `+918056494838`.
- **Honest Data States**: Transparently identifies whether a request was *Prepared*, *Sent to WhatsApp*, or *Saved in Local System*.

### 4. Technician & Owner Portal
- Accessible discreetly via top bar or footer.
- Real-time inbox of all incoming customer requests.
- Search and filter by customer name, phone, ticket ID, or status (`New`, `Contacted`, `In Progress`, `Completed`).
- 1-click **Call Customer** and **Chat on WhatsApp** buttons.
- 1-click **Export to CSV** for spreadsheets.
- Service categories manager to add, edit, or delete live services.

### 5. Local SEO & Search Readiness
- Semantic HTML5 headings (`h1`, `h2`, `h3`) and descriptive image alt tags.
- Optimized title: *"ISM ENGINEERING | AC Repair & Home Appliance Service in Tirupur"*.
- Meta description and Open Graph tags.
- Schema.org `HomeAndConstructionBusiness` structured data with exact coordinates, address, and telephone number.
- `public/robots.txt` and `public/sitemap.xml`.
- Direct Google Maps directions link for 166, VGV Garden, Thirumurugan Poondi.

---

## 💻 Commands

### 1. Install Dependencies
```bash
npm install
```

### 2. Run Development Server
```bash
npm run dev
```
Runs the Vite development server locally at `http://localhost:5173`.

### 3. Build for Production
```bash
npm run build
```
Creates an optimized production build in the `dist/` directory.

### 4. Preview Production Build
```bash
npm run preview
```

---

## 🗄️ Backend Service (Optional Cloud Storage & Database)
A complete, production-ready backend is included in the `server/` directory:
- Express server with `helmet` security headers and rate limiting.
- `multer` photo upload validation (MIME types, 5MB limit).
- Protected admin endpoints via `x-admin-key`.
- To run:
  ```bash
  cd server
  npm install
  npm start
  ```
- To connect the frontend to the backend, set the environment variable:
  ```env
  VITE_API_URL=http://localhost:5000
  ```

---

## 🌐 Publishing to Production (Custom Domain & HTTPS)

### Option A: Vercel / Netlify (Recommended for Frontend)
1. Push this repository to GitHub or GitLab.
2. Link the repository to **Vercel** or **Netlify**.
3. Build Settings:
   - Build Command: `npm run build`
   - Output Directory: `dist`
4. Add Custom Domain:
   - Under Project Settings > Domains, enter your domain: `ismengineering.in`.
   - Configure DNS records (CNAME or A record pointing to Vercel/Netlify).
   - SSL/HTTPS certificate will be provisioned automatically for free.

### Option B: Cloudflare Pages
1. Connect Git repository to Cloudflare Pages.
2. Framework preset: **Vite**, Output directory: `dist`.
3. Enable Cloudflare SSL/TLS in Full (Strict) mode.

### Option C: Ubuntu / Linux VPS with Nginx & Let's Encrypt
1. Build the production files: `npm run build`.
2. Copy `dist/` to `/var/www/ismengineering.in`.
3. Configure Nginx server block:
```nginx
server {
    listen 80;
    server_name ismengineering.in www.ismengineering.in;
    root /var/www/ismengineering.in;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }

    location ~* \.(js|css|png|jpg|jpeg|gif|ico|svg|webp)$ {
        expires 1y;
        add_header Cache-Control "public, no-transform";
    }
}
```
4. Secure with free SSL certificate:
```bash
sudo certbot --nginx -d ismengineering.in -d www.ismengineering.in
```
