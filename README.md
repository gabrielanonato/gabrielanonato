# Data Analyst Portfolio — GitHub Pages (Jekyll, Minima)

A clean, recruiter-friendly portfolio template for data analysts. Built with **GitHub Pages** using the **minima** theme so you can deploy in minutes.

## 🚀 Quick start
1. Create a repo named `<your-user>.github.io` on GitHub.
2. Download this template and push all files to that repo.
3. In repo **Settings → Pages**, ensure "Deploy from branch" is enabled (default for user site).
4. Your site will be live at `https://<your-user>.github.io`.

## 🛠 Customize
- Edit `_config.yml` (title, description, links).  
- Update `about.md` and `contact.md`.  
- Replace placeholder links inside each project page.  
- Drop screenshots into `assets/img/` and reference them like `/assets/img/your-image.png`.  
- Add more projects by copying one of the files in `/projects` and updating the front matter.

## 🧩 Notes
- This template uses the **minima** theme and `jekyll-seo-tag` plugin (both supported by GitHub Pages).  
- If you use a **project site** instead of user site, set `baseurl: "/your-repo-name"` in `_config.yml` and prefix internal links with `{{ site.baseurl }}`.

## 🧪 Local preview (optional)
If you want to run locally:
```bash
gem install bundler jekyll
bundle init && bundle add jekyll minima jekyll-seo-tag
bundle exec jekyll serve
```
Then open http://localhost:4000
