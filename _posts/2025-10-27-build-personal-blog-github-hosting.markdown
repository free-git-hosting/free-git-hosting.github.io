---
layout: post
title: "How I Built My Personal Blog Using GitHub Hosting"
description: "Learn step-by-step how to build and host a personal blog using GitHub Hosting. This guide covers setup, customization, analytics, and optimization for beginners."
image: assets/images/featured_build-personal-blog-github-hosting.webp
featured: false
author: CodingRhodes
---

Creating a personal blog doesn’t have to be complicated or expensive. With **GitHub Hosting**, anyone — from tech enthusiasts to complete beginners — can launch a professional, fast, and secure blog for free.

In this article, I’ll walk you through exactly **how I built my personal blog using GitHub Hosting**, from setting up the repository and customizing the theme to optimizing it for SEO and Google Discover visibility. Whether you’re an aspiring developer, writer, or freelancer, this detailed guide will help you understand the power of GitHub Pages and how to use it as your blog’s home.

---

## Introduction: Why I Chose GitHub Hosting for My Blog

When I first decided to start a personal blog, I wanted three things — **simplicity, speed, and zero cost**. I explored platforms like WordPress, Medium, and Ghost, but they all had limitations or costs attached. Then I discovered **GitHub Hosting** through GitHub Pages — a feature that allows users to host static websites directly from their GitHub repositories.

GitHub Hosting was perfect for me because:

* It’s **completely free** for public repositories.
* It supports **custom domains and HTTPS** for professional credibility.
* It’s **developer-friendly**, especially with **Jekyll**, a static site generator designed for GitHub Pages.

In this article, I’ll explain how I transformed a simple repository into a fully functional personal blog optimized for SEO and mobile performance.

---

## Step 1: Setting Up the GitHub Repository

Before creating your blog, you need a GitHub account. Once you have one:

1. Go to **github.com/new** and create a new repository.
2. Name it in this format: `username.github.io` (replace *username* with your GitHub username).
3. Choose **Public** repository visibility.
4. Check the box to **Initialize this repository with a README**.
5. Click **Create Repository**.

Once your repository is ready, GitHub automatically enables **GitHub Pages** for it. This means your blog will be accessible at `https://username.github.io` after publishing.

---

## Step 2: Choosing a Blogging Framework – Why I Picked Jekyll

GitHub Hosting works perfectly with **Jekyll**, a lightweight static site generator. Jekyll converts Markdown files into a static website, which is ideal for blogs.

Here’s why Jekyll made sense for me:

* It integrates directly with **GitHub Pages** (no external hosting setup required).
* Posts are written in **Markdown**, making it beginner-friendly.
* There are thousands of **free and open-source Jekyll themes**.

### Installation

If you want to run Jekyll locally before uploading it to GitHub:

```bash
gem install jekyll bundler
jekyll new myblog
cd myblog
bundle exec jekyll serve
```

Then, open your browser and go to `http://localhost:4000` to preview your blog.

After testing locally, you can push the code to your GitHub repository.

---

## Step 3: Selecting a Jekyll Theme

One of the biggest advantages of Jekyll and GitHub Hosting is theme flexibility.

You can:

* Use **official Jekyll themes** from [jekyllrb.com/themes](https://jekyllrb.com/themes/)
* Fork an open-source theme from GitHub (many are optimized for blogs)
* Or create your own theme using HTML, CSS, and Liquid templates

I selected a minimalistic theme with:

* A clean, mobile-friendly layout
* Built-in SEO support
* Fast-loading performance for Google Discover

To apply a theme, edit your `_config.yml` file:

```yaml
theme: minima
title: My Personal Blog
description: Sharing my thoughts on technology, design, and development.
author: Your Name
```

Once committed, GitHub will automatically rebuild your site.

---

## Step 4: Writing and Structuring Blog Posts

Jekyll stores posts inside the `_posts` folder. Each post file follows a naming convention: `YYYY-MM-DD-title.md`.

Example:

```markdown
---
layout: post
title: "My First Blog Post"
date: 2025-10-27
---

This is my very first post on GitHub Hosting. I’ll be writing about web development, blogging, and online tools.
```

GitHub Pages automatically detects Markdown files and converts them into web pages.

### Structuring Your Content

Organize your content under clear categories, such as:

* **Tech Tutorials**
* **Coding Projects**
* **Personal Stories**
* **Productivity Tips**

This structure helps both readers and search engines understand your content better.

---

## Step 5: Adding a Custom Domain

Even though your site is hosted under `username.github.io`, having a **custom domain** makes it look professional.

Here’s how to do it:

1. Purchase a domain from providers like **Namecheap** or **Google Domains**.
2. In your repository, go to **Settings → Pages → Custom domain**.
3. Enter your domain (for example, `www.myblog.com`).
4. Update your DNS settings with:

   * Type: `CNAME`
   * Name: `www`
   * Value: `username.github.io`

GitHub will automatically enable **SSL/HTTPS** for security.

---

## Step 6: Enhancing SEO for GitHub-Hosted Blogs

Search Engine Optimization (SEO) is vital for visibility, especially if you aim to appear on **Google Discover**.

### Basic SEO Steps

1. Add a `meta_description` in your `_config.yml` file.
2. Use descriptive titles and headers (H1, H2, H3).
3. Include internal links between related blog posts.
4. Add `alt` text for all images.

### Advanced SEO Tips for GitHub Hosting

* Generate a **sitemap.xml** using the Jekyll Sitemap plugin.
* Add an **RSS feed** using `jekyll-feed`.
* Submit your site to **Google Search Console** for indexing.

Example plugin setup in `_config.yml`:

```yaml
plugins:
  - jekyll-feed
  - jekyll-sitemap
```

---

## Step 7: Tracking Performance with GitHub Analytics

While GitHub Pages doesn’t include analytics by default, you can integrate **Google Analytics** or **Plausible Analytics**.

### Adding Google Analytics

1. Create an Analytics account at [analytics.google.com](https://analytics.google.com).
2. Copy the tracking code.
3. Add it to your `_includes/head.html` file:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-XXXXXX-X"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'UA-XXXXXX-X');
</script>
```

This helps you monitor visitor behavior, top-performing pages, and engagement.

---

## Step 8: Optimizing for Mobile Devices

Since Google prioritizes **mobile-first indexing**, your blog must be responsive.

Tips to optimize for mobile:

* Use a responsive Jekyll theme.
* Avoid large images; compress using **TinyPNG** or **ImageOptim**.
* Use readable fonts and sufficient spacing.
* Test your site with Google’s **Mobile-Friendly Test Tool**.

GitHub Hosting easily serves lightweight static pages, ensuring your blog loads quickly on mobile.

---

## Step 9: Automating Updates with GitHub Actions

GitHub Actions allows you to automate blog deployment.

For example, you can automatically rebuild your Jekyll site every time you push new content.

Sample GitHub Actions workflow (`.github/workflows/jekyll.yml`):

```yaml
name: Jekyll Site CI
on:
  push:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Build the site
        run: bundle exec jekyll build
      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./_site
```

This automation ensures your blog is always up to date without manual uploads.

---

## Step 10: Promoting Your GitHub-Hosted Blog

Once your blog is live, promote it to attract readers:

* Share posts on **LinkedIn, X (Twitter), and Reddit**.
* Add your blog to **developer directories**.
* Collaborate with other GitHub bloggers.
* Create SEO-rich content around keywords like **“GitHub Hosting”** and **“GitHub Pages blog tutorial.”**

Consistency and SEO optimization will gradually improve visibility on **Google Discover**.

---

## Common Mistakes to Avoid

1. **Ignoring SEO metadata** – Every page should have a title and description.
2. **Using large, unoptimized images** – Slows down loading times.
3. **Not customizing themes** – Make your blog unique.
4. **Forgetting analytics** – You can’t improve what you don’t measure.
5. **Neglecting mobile experience** – Most readers browse on phones.

---

## Conclusion: Why GitHub Hosting Is Perfect for Personal Blogs

Using **GitHub Hosting** for my personal blog turned out to be one of the smartest decisions I made. It’s free, scalable, and surprisingly professional when customized right. The integration with Jekyll makes publishing effortless, and GitHub’s built-in version control ensures every change is tracked.

If you’re someone who wants to own your content, customize it freely, and understand how your website works under the hood, **GitHub Hosting** is the perfect starting point.

Your next step? Start small. Create a repository, experiment with Jekyll, and publish your first post today.

---
