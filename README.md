# FirstCry Intellitots Preschool — Website & School Management System Plan

## 1. Executive Summary
A production-ready, mobile-first website and integrated school management system for **FirstCry Intellitots Preschool** in Ranchi, designed to serve parents, staff, and management with clear enrolment, fee tracking, and scalable modules for future growth.

**Address**: House No. 441-A, Road No. 5, Ashok Nagar, Ranchi, Jharkhand, India

---

## 2. Goals & Success Criteria
- Provide parent-friendly access to school information and admission services.
- Enable efficient staff workflows for enrolment, fee collection, and reporting.
- Provide management dashboards for fee health and enrolment statistics.
- Lay a modular foundation for future features (attendance, transport, communication, exams).
- Ensure accessibility, security, and performance on low-end mobile devices.

---

## 3. Information Architecture & Navigation
### Top Horizontal Navigation (Desktop) / Hamburger (Mobile)
1. **About Us**
   - School Overview
   - Vision & Mission
   - Curriculum & Teaching Methodology
   - Facilities & Safety
   - Contact Information & Location Map

2. **Unit Selection**
   - **Manage Units** (Add/Edit/Delete units, assign code & address)
   - **Manage Users** (Add/Edit/Delete users, link to units)
   - **Assign Roles** (Admin, Teacher, Accountant, Principal, Super Admin)
   - **Manage Roles & Permissions** (RBAC module configuration)

3. **Student Enrolment**
   - **Add Student** (Online admission form + document upload)
   - **List Students** (Search, filters, pagination)
   - **Edit Student** (Profile, status: Applied / Enrolled / Withdrawn)

4. **Student Services**
   - **ID Card Details** (Generate printable layout / PDF)
   - **Bonafide Certificate** (Auto-generate with letterhead)
   - **Transfer Certificate** (Auto-generate + history log)

5. **Fees**
   - **Create Fee Structure** (Fee heads + cycles)
   - **List Fee Structure**
   - **Assign Fee Structure** (Class/section/student)
   - **Collect Fee** (Partial payments, discounts, online/offline)
   - **Generate Invoice / Fee Receipts** (PDF + share via email/SMS/WhatsApp)
   - **Fee Reminders & Alerts** (Scheduled, overdue alerts)

6. **Reports**
   - Student Reports
   - Fee Reports
   - Transport Reports (future)
   - Export: Excel/CSV/PDF

7. **Future Modules**
   - Attendance
   - Transport Management
   - Class Assignment
   - Communication

**Accessibility & Responsiveness**
- Fully accessible navigation with focus states, ARIA labels, and keyboard navigation.
- Mobile-first layout with collapsible menu and large tap targets.

---

## 4. UX/UI Design System
### Visual Style
- **Palette**: pastel blue, mint green, soft yellow, with coral or teal for CTAs.
- **Typography**: Poppins or Inter for clarity and friendly tone.
- **Illustrations**: small playful icons (toys, books, pencils) for warmth.

### UX Principles
- Simple workflows with minimal steps for routine actions.
- Inline validation + progressive disclosure for complex forms.
- Clear status badges: `Paid`, `Pending`, `Overdue`.
- Confirmation modals for sensitive actions (delete, payment submission).

### Mobile-First Implementation
- Multi-step forms with progress indicators.
- Input masks for phone & date fields.
- Optimized for 360px width and low bandwidth.

---

## 5. Core Functional Modules
### 5.1 Student Enrolment
**Key Features**
- Admission form with validation and document uploads.
- Status tracking: Applied → Enrolled → Withdrawn.

**Core Fields**
- Student name, DOB, gender, class/grade, section
- Parent/guardian details, address, contact numbers, email
- Unit/branch, transport requirement, emergency contact

**Validation Rules**
- Required: student name, DOB, parent contact, class, unit.
- Email format validation.
- Phone input masks.
- File upload type restrictions (PDF/JPG/PNG).

### 5.2 Fees Management
**Key Features**
- Define fee heads and cycles.
- Assign to class or student.
- Record payments (partial, discount, waiver).
- Auto-generate receipts and invoice PDFs.
- Scheduled reminders and overdue alerts.

### 5.3 Reports & Analytics
- Dashboard summary cards: Total Students, Fees Collected, Pending Fees, Overdue Count.
- Charts for trends (bar/line/pie).
- Export options (CSV/PDF/Excel).

---

## 6. Detailed User Flows
### A. Parent (Prospective)
1. Visit homepage → view About Us → facilities → contact.
2. Submit enquiry (phone/email form).

**Layout**: hero section + facilities cards + enquiry form.
**Success State**: "Thanks! We’ll contact you within 24 hours."

---

### B. Admin – Student Enrolment
1. Login → Select Unit → Student Enrolment → Add Student.
2. Fill form + upload documents → Save.
3. Optional: Assign fee structure and class.

**Validation**
- Required fields highlighted.
- Inline field errors (e.g., "Please enter a valid date of birth").

**Success State**
- Confirmation toast: "Student profile created successfully."

---

### C. Admin/Accountant – Fee Collection
1. Login → Select Unit → Fees → Collect Fee.
2. Search student → view fee structure → mark payment.
3. Generate receipt and optionally send SMS/email.

**Error State**
- "Payment amount exceeds pending dues."

**Success State**
- Receipt PDF generated with share options.

---

### D. Management – View Fee Reports
1. Login → Reports → Fee Dashboard.
2. View charts by unit, class, date range.

**Success State**
- Charts rendered with filters saved per user.

---

### E. System – Fee Reminders
1. Admin sets rules (e.g., 3 days before due, 7 days overdue).
2. System sends automated reminders via SMS/email.

**Parent Message Example**
- "Friendly reminder: Rahul’s fee for April is due on 05-May. Pay online here: [link]."

---

## 7. Content & Microcopy Guidelines
### Homepage Hero (Sample Copy)
“Welcome to **FirstCry Intellitots Preschool** in Ashok Nagar, Ranchi — a joyful, safe, and nurturing space where little learners thrive. Play-based learning, caring teachers, and a focus on early childhood growth.”

### About Us (Vision & Mission)
- **Vision**: “To inspire curiosity, creativity, and confidence in every child.”
- **Mission**: “We provide a safe, joyful environment that nurtures foundational learning through play, exploration, and care.”

### Contact Page
- Address: House No. 441-A, Road No. 5, Ashok Nagar, Ranchi
- Phone: +91-XXXXXXXXXX
- Email: contact@firstcryintellitots.in

### Microcopy Examples
- Buttons: “Add Student”, “Collect Fee”, “Generate ID Card”, “Save & Continue”
- Reminders: “Payment due in 3 days”, “Overdue by 7 days”
- Errors: “Please upload a valid document (PDF/JPG/PNG)”

---

## 8. Accessibility & Performance
- ARIA labels for navigation & form elements.
- High contrast text and focus outlines.
- Lazy loading of images.
- Code splitting & caching in production builds.

---

## 9. Technology Stack Recommendation
### Recommended Stack
- **Frontend**: Next.js (React) + Tailwind CSS
- **Backend**: Node.js + Express
- **Database**: PostgreSQL
- **API**: REST (with structured endpoints for future mobile apps)
- **Auth**: JWT + RBAC

**Why this stack?**
- Next.js offers SEO for public pages and fast rendering.
- Tailwind ensures consistent, responsive styling.
- Express + PostgreSQL supports scalability and structured data.

---

## 10. Integrations
- **Payment Gateway**: Razorpay or PayU (India optimized).
- **Email**: SendGrid / Amazon SES.
- **SMS/WhatsApp**: Twilio, MessageBird, or local Indian providers.
- **Maps**: Google Maps embed.

---

## 11. Deployment & Hosting Plan
- **Hosting**: AWS (EC2 + RDS), or DigitalOcean App Platform for simplicity.
- **CI/CD**: GitHub Actions for automated builds and deployment.
- **SSL**: Let’s Encrypt with auto-renewal.

### Domain Suggestions
- firstcryintellitotsranchi.in
- firstcryintellitots.in

### DNS Setup
- **A record** → server IP
- **CNAME** → www to root domain
- **TXT** → domain verification for email services

---

## 12. Sitemap
```
/
├── Home
├── About Us
│   ├── School Overview
│   ├── Vision & Mission
│   ├── Curriculum & Teaching Methodology
│   ├── Facilities & Safety
│   └── Contact & Location Map
├── Unit Selection
│   ├── Manage Units
│   ├── Manage Users
│   ├── Assign Roles
│   └── Manage Roles & Permissions
├── Student Enrolment
│   ├── Add Student
│   ├── List Students
│   └── Edit Student
├── Student Services
│   ├── ID Card Details
│   ├── Bonafide Certificate
│   └── Transfer Certificate
├── Fees
│   ├── Create Fee Structure
│   ├── List Fee Structure
│   ├── Assign Fee Structure
│   ├── Collect Fee
│   ├── Generate Invoice / Receipt
│   └── Fee Reminders & Alerts
├── Reports
│   ├── Student Reports
│   ├── Fee Reports
│   └── Export
└── Future Modules
    ├── Attendance
    ├── Transport Management
    ├── Class Assignment
    └── Communication
```

---

## 13. Wireframe Descriptions (Text)
### Homepage
- **Hero**: Title, short intro, CTA buttons (Enquire Now / Call Us).
- **Key Highlights**: 3–4 cards (Safety, Play-Based Learning, Experienced Staff).
- **Facilities**: icon grid.
- **Testimonials**: parent quotes.
- **Footer**: contact info + map.

### About Us
- Banner header + mission/vision cards.
- Curriculum section with illustrated icons.
- Facilities gallery.
- Contact block with embedded map.

### Student Enrolment
- Multi-step form: Student Info → Parent Info → Documents → Review.
- Progress indicator on top.
- Save as draft + Submit button.

### Fees → Collect Fee
- Search bar with filters.
- Student summary card.
- Fee breakdown table (due/paid balance).
- Payment form with method selection + receipt preview.

### Reports Dashboard
- Top row summary cards.
- Tabs for “Students” and “Fees”.
- Charts with filters.
- Export button (CSV/PDF).

---

## 14. Implementation Checklist
1. Finalize brand palette, typography, and logo assets.
2. Build responsive UI components in Next.js + Tailwind.
3. Implement authentication + RBAC.
4. Develop core modules: enrolment, fee management, reports.
5. Integrate payment and notification services.
6. QA testing for mobile, performance, accessibility.
7. Deploy to production with CI/CD.
8. Train staff and monitor initial usage.

---

## 15. Development Notes (Future Scalability)
- Keep APIs modular with versioning.
- Use feature flags for upcoming modules.
- Maintain consistent UI components for quick additions.

