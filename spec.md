# NextGen IT Hub

## Current State
Full-stack platform with Home, Shop, Converter, Image Tools, Job Updates, Gov Documents, Contact Us, AI Chat pages. Navigation bar, cart, auth, admin panel all working.

## Requested Changes (Diff)

### Add
- New page: Certificate Album Sheet (`/certificate-album`) — a browser-based tool to design and print certificates and photo album sheets
- Navigation bar entry: "Certificate Album" (or "Cert & Album")
- Page features:
  - Two tabs: "Certificate" and "Album Sheet"
  - **Certificate tab:** Fill in fields (Recipient Name, Course/Achievement Title, Date, Issued By/Organization, optional subtitle), choose border style (Classic Gold, Blue Formal, Green Nature, Red Royal), preview live certificate, Print/Download as PNG button
  - **Album Sheet tab:** Choose layout (2x2, 2x3, 3x3 photo grid), upload photos (drag-drop or file picker), fill caption per photo slot, preview full sheet, Print/Download button
  - Client-side only — no server uploads
  - Print uses `window.print()` with proper CSS print styles so only the certificate/album is printed

### Modify
- `App.tsx` — add `"certificate-album"` page type and render `<CertificateAlbumPage />`
- `Header.tsx` — add "Cert & Album" nav link

### Remove
- Nothing

## Implementation Plan
1. Create `src/frontend/src/pages/CertificateAlbumPage.tsx` with two tabs: Certificate maker and Album Sheet maker
2. Certificate tab: form fields + live preview canvas/div + print/download
3. Album Sheet tab: grid layout selector + photo upload per slot + captions + print/download
4. Update `App.tsx` to add the new page type and route
5. Update `Header.tsx` to add navigation item
6. Validate (lint + build)
