# av-site

This repository contains the source files for **alisonvermaat.com**, the portfolio website for stylist **Alison Vermaat** in Montreal.  
The project is structured so that *all content and metadata live in Markdown/YAML*, and the final HTML pages in `site/` can be built or updated from that source.

---

## 📁 Project Structure

```
alisonvermaat-site/
  content/
    media.yml              # Central index of all images and metadata
    images-master.md       # References to portraits, certificate, hero images
    portfolio-images.md    # Gallery/portfolio ordering
    booking.md             # Square booking URL + CTA text
    bio.md                 # Short + long biography text
  assets/
    images/                # Web-ready images only (JPG/PNG/WebP)
  site/
    index.html             # Main homepage (generated or edited by hand)
    about.html             # About page
    portfolio.html         # Portfolio / gallery page
  README.md
```

---

## 🖼 Image Workflow

### **Where images live**
- All *web-ready* images go in:  
  `assets/images/`

- **Do not store TIFFs or giant source files** in the repo.  
  Keep high-resolution masters separately.

### **Image formats**
- Portfolio photos → **WebP**
- Portraits → **WebP**
- Certificate scan → **JPEG**
- Logos → **PNG** or **SVG**

---

## 🧩 `media.yml` — Master Image Index

All image metadata is stored in:

```
content/media.yml
```

Each image entry uses a predictable structure:

```yaml
images:
  portrait_main:
    file: assets/images/portrait-main.webp
    date: 2025-01-10
    location: Montreal
    alt: Portrait of Alison Vermaat.
    caption: Alison in her Montreal studio.
    roles: [hero, about-page]
    tags: []
```

### What this gives you
- One central place to edit image info  
- HTML pages can reference images by **key**, not by path  
- Easy to generate galleries, hero images, and sections

---

## 🧾 Markdown Files

### **`content/images-master.md`**
References key images:

```md
hero: portrait_main
certificate: hwk_certificate
```

### **`content/portfolio-images.md`**
Defines gallery order:

```md
- work_2023_montreal_updo
- work_2020_montreal_color
- work_2018_berlin_bob
```

### **`content/booking.md`**
Contains Square booking URL and CTA text.

### **`content/bio.md`**
Contains both short and long biography formats.

---

## 🌐 `site/` Directory

Holds the *actual website pages* (`index.html`, `about.html`, `portfolio.html`).

These pages can be generated from the content files, or edited manually.

---

## 🧪 Workflow for Editing Content

1. Add or optimize image files → `assets/images/`
2. Add matching metadata → `content/media.yml`
3. Reference images → `content/images-master.md` or `content/portfolio-images.md`
4. Commit and push:
   ```
   git add .
   git commit -m "Update images and metadata"
   git push
   ```
5. Update HTML in `/site` as needed.

---

## 🛠 Future Enhancements (Optional)

- Build script to generate HTML automatically from Markdown/YAML  
- Minimize images on import  
- Deploy using GitHub Pages  

---

This project is built so that **content is completely decoupled from layout**, making it easy to edit or rebuild the site without touching HTML.
