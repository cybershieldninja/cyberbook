# 📚 Cybersecurity & Cloud Engineering Series

Welcome to our multi-book series dedicated to professionals in cybersecurity, cloud architecture, and infrastructure engineering.

Hosted as a static site for engineers, analysts, and executives.
![MkDocs](https://img.shields.io/badge/Built%20with-MkDocs-0052cc?logo=readthedocs)

## 🛠 Installation & Development

### 1. 🐍 Install dependencies

```bash
pip install mkdocs mkdocs-material

pip freeze > requirements.txt

```
### 2. ▶️ Serve locally
```bash
mkdocs serve
```
Then open http://localhost:8000

### 3. ⚙️ Build for production
```bash
mkdocs build
```

## 🌐 Deployment — Cloudflare Pages

This project is deployed using **[Cloudflare Pages](https://pages.cloudflare.com/)**.

📖 **Live Site:** [https://cyberbook.pages.dev/](https://cyberbook.pages.dev/)

### 🛠 Deploy Instructions (for contributors)

1. Push to the `main` branch (or the branch you've configured in Cloudflare Pages).
2. Cloudflare Pages will automatically:
   - Install dependencies via `pip install -r requirements.txt`
   - Build the static site using `mkdocs build`
   - Deploy the contents of the `site/` directory

> ⚠️ Make sure your `mkdocs.yml` and all Markdown files are inside the `/docs` folder, or adjust the Pages settings accordingly.

---

## 🖼️ License

Content licensed under Creative Commons BY 4.0