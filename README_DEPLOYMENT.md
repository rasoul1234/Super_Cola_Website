# Super Cola Website

A modern, responsive static website for Super Cola — proudly made in Herat, Afghanistan. The site showcases our refreshing products with an engaging user interface built with HTML, CSS, and JavaScript.

## 🌐 Features

- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Modern UI/UX**: Clean, vibrant interface with smooth animations
- **Product Showcase**: Display water subscription plans and product offerings
- **Interactive Components**: Carousel (Swiper), scroll reveal animations, and dynamic navigation
- **Multi-page Structure**: Home, About, Shop, Water, and Contact pages
- **Optimized Performance**: Bundled assets and CDN-loaded libraries for fast loading

## 📁 Project Structure

```
Super_Cola_Website/
├── index.html              # Home page
├── water.html              # Water subscription plans
├── about1.html             # About us page
├── shop.html               # Product shop
├── contact.html            # Contact page
├── style.css               # Main CSS (root level)
├── app.js / app1.js        # JavaScript files (root level)
├── assets/
│   ├── css/
│   │   ├── styles.css
│   │   └── swiper-bundle.min.css
│   ├── img/                # Product and UI images
│   ├── js/
│   │   ├── main.js
│   │   ├── scrollreveal.min.js
│   │   └── swiper-bundle.min.js
│   └── scss/               # SCSS source files (for development)
├── img/                    # Secondary images folder
├── requirements.txt        # Python dependencies (optional, for deployment)
└── README_DEPLOYMENT.md    # This file
```

## 🚀 Getting Started

### Local Development

1. **Clone or download the project**
   ```bash
   git clone <your-repo-url>
   cd Super_Cola_Website
   ```

2. **Serve locally with Node http-server**
   ```bash
   npx http-server -p 8089
   ```
   Then open `http://localhost:8089` in your browser.

3. **Or use Python's built-in server**
   ```bash
   python -m http.server 8000
   ```
   Then open `http://localhost:8000` in your browser.

## 🛠️ Technologies Used

### Frontend Libraries (Client-side)
- **[Remix Icon](https://remixicon.com/)** (v4.2.0) — Icon library via CDN
- **[Swiper](https://swiperjs.com/)** — Carousel/slider component (bundled locally)
- **[ScrollReveal](https://scrollrevealjs.org/)** — Scroll animation library (bundled locally)
- **[Font Awesome](https://fontawesome.com/)** (optional, in contact.html)

### Development Tools
- **HTML5** — Semantic markup
- **CSS3** — Styling and animations
- **JavaScript (Vanilla)** — Interactive features
- **SCSS** — Preprocessor for stylesheets (source in `assets/scss/`)

### Optional: Python Deployment
If deploying with a Python WSGI server:
- **Flask** — Micro web framework
- **Gunicorn** — Production WSGI HTTP server
- **WhiteNoise** — Efficient static file serving

## 📦 Installation

### No Installation Required (Static Site)
This is a static website — just open `index.html` in any modern browser or host it on any static hosting platform.

### Optional: Python Dependencies (for WSGI deployment)
```bash
pip install -r requirements.txt
```

This installs Flask, Gunicorn, and WhiteNoise for Python-based deployments.

## 🌍 Deployment Options

### Option 1: Static Hosting (Recommended)
No Python packages required. Upload the entire project folder to:
- **GitHub Pages**: Commit to a `gh-pages` branch or use GitHub Actions
- **Netlify**: Drag & drop the folder or connect to GitHub
- **Vercel**: Connect your repository
- **AWS S3 + CloudFront**: Upload files to S3 and configure CloudFront

### Option 2: Python WSGI Server (Flask + Gunicorn)
For platforms like Heroku, Railway, or a VPS:

1. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

2. **Create `server.py`** (example below)
   ```python
   from flask import Flask
   from whitenoise import WhiteNoise

   app = Flask(__name__, static_folder='.', static_url_path='')
   app.wsgi_app = WhiteNoise(app.wsgi_app, root='.')

   @app.route('/')
   def index():
       return app.send_static_file('index.html')

   if __name__ == '__main__':
       app.run(debug=False)
   ```

3. **Run locally**
   ```bash
   python server.py
   ```
   Visit `http://localhost:5000`

4. **Deploy to Heroku** (example)
   ```bash
   heroku create super-cola-site
   git push heroku main
   ```

### Option 3: Docker
Create a `Dockerfile` to containerize the site (I can provide one on request).

## 📝 Configuration

### Contact Information
Update the following in the HTML files:
- **Email**: Change `info@supercola.com` to your email
- **Phone**: Update phone numbers in contact sections
- **WhatsApp Links**: Modify the WhatsApp API URLs in `water.html` and other pages
- **Social Links**: Update Facebook, Twitter, Instagram links in the footer

### Branding
- **Logo**: Replace `assets/img/super-cola.png` with your logo
- **Colors**: Modify CSS variables in `assets/css/styles.css`
- **Text**: Update product names, descriptions, and delivery info as needed

## 🎨 Customization

### Styling
- Main styles: `assets/css/styles.css`
- Component styles: `assets/scss/components/` (SCSS source files)
- To rebuild CSS from SCSS, use a SCSS compiler (e.g., `sass` CLI or a build tool)

### JavaScript
- Main script: `assets/js/main.js`
- Swiper initialization and ScrollReveal setup are included

### Images
- Product images: `assets/img/`
- Secondary images: `img/`
- Update image paths if reorganizing folders

## ✅ Quality Checklist

- [x] Semantic HTML5 structure
- [x] Responsive design (mobile-first approach)
- [x] Bundled JavaScript and CSS assets
- [x] CDN fallbacks for icon libraries
- [x] Optimized image assets
- [x] Clean, commented code
- [x] Cross-browser compatible

## 🐛 Known Issues & Notes

- Multiple `id="contact"` sections exist in `water.html` (now unique: `contact-monthly`, `contact-6months`, `contact-annual`)
- Some images reference both `assets/img/` and `img/` folders — consolidate if needed for cleaner deployment
- The site currently uses `super-cola.png` as the logo (ensure this file exists in `assets/img/`)

## 📞 Support & Maintenance

- **Logo/Branding Updates**: Replace image files in `assets/img/`
- **Content Updates**: Edit HTML files directly or use a static site generator if scaling
- **Performance**: Minify CSS/JS for production if not already done
- **Analytics**: Add Google Analytics or similar by including a tracking script in `index.html`

## 📄 License

This project is created for Super Cola. Modify and use as needed.

---

**Deployment Ready**: The site is ready to deploy to any static host (GitHub Pages, Netlify, Vercel) or a Python WSGI server (Heroku, Railway, VPS).

For detailed deployment steps, see the **[Deployment Options](#-deployment-options)** section above.
