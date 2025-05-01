---
layout: post
title: "Integrating Custom Domains with GitHub Pages: A Complete Guide"
categories: [Web Hosting, GitHub, Domains, Web Development, Jekyll]
tags: [github hosting, custom domain setup, github pages, website deployment, DNS configuration]
description: "Learn how to connect a custom domain with GitHub Pages. Step-by-step guide to GitHub hosting, DNS setup, HTTPS, and troubleshooting tips."
image: assets/images/featured_connect-custom-domain-github-pages.webp
featured: false
---

Integrating a custom domain with GitHub Pages allows developers and website owners to present a professional, branded URL while leveraging the power of GitHub hosting. 

Whether you're launching a personal portfolio, a project page, or a business website, connecting a custom domain enhances credibility and discoverability. 

In this comprehensive, beginner-friendly guide, you’ll learn how to map a custom domain to your GitHub Pages site, configure DNS records correctly, ensure HTTPS security, and troubleshoot common issues. From domain registrars to GitHub repository settings, every step is covered.

---

## Understanding GitHub Hosting with Pages

### What is GitHub Pages?
GitHub Pages is a free hosting service that allows you to publish static websites directly from a GitHub repository. It supports HTML, CSS, JavaScript, and static site generators like Jekyll.

#### Key Benefits:
- Free and fast static website hosting
- Easy integration with version control
- Supports custom domains and HTTPS
- Ideal for portfolios, documentation, and project sites

### Limitations to Consider
- Not suitable for dynamic websites or server-side scripts
- Bandwidth limits apply to high-traffic sites
- Third-party services are needed for forms and databases

---

## Choosing and Purchasing a Custom Domain

![Screenshot of a GitHub repository with a standard Jekyll folder structure]({{ site.baseurl }}/assets/images/Choosing-and-Purchasing-Custom-Domain.webp)

### Step-by-Step Guide to Domain Purchase
1. Choose a domain registrar (e.g., Namecheap, GoDaddy, Google Domains).
2. Search for your desired domain name.
3. Register the domain and create an account.
4. Retain access to the DNS settings dashboard.

### Factors to Consider
- Relevance to your brand or name
- Extension (.com, .dev, .io, etc.)
- Pricing and renewal costs
- DNS management options

---

## Preparing Your GitHub Repository

### Creating a GitHub Pages Repository
1. Log into GitHub and create a new repository.
2. Name it `username.github.io` for a user/organization site, or any name for a project site.
3. Push your website files (e.g., `index.html`, CSS, JS, or Jekyll project) to the repository.

### Enabling GitHub Pages
1. Go to your repository’s **Settings** > **Pages**.
2. Under **Source**, choose the branch (usually `main`) and root directory or `/docs` folder.
3. Click **Save**.
4. GitHub will provide a default `.github.io` subdomain URL.

---

## Pointing Your Custom Domain to GitHub Pages

### Configuring DNS Records
Navigate to your domain registrar’s DNS settings and add the following records:

![Diagram showing DNS configuration with A and CNAME records pointing to GitHub Pages.]({{ site.baseurl }}assets/images/Configuring-DNS-Records.webp)

#### For Apex Domains (e.g., example.com):
- **Type**: A
- **Name**: @
- **Value**:
  - 185.199.108.153
  - 185.199.109.153
  - 185.199.110.153
  - 185.199.111.153

#### For Subdomains (e.g., www.example.com):
- **Type**: CNAME
- **Name**: www
- **Value**: `username.github.io`

### Setting Up the `CNAME` File
In the root of your GitHub repository:
1. Create a file named `CNAME` (no extension).
2. Add your domain name in plain text (e.g., `www.example.com`).
3. Commit the file to the repository.

### Enforcing HTTPS
1. Return to **Settings > Pages**.
2. After DNS resolves, check **“Enforce HTTPS.”**
3. GitHub will provision an SSL certificate.

---

## Verifying Domain Connection

### DNS Propagation Time
- DNS changes can take anywhere from a few minutes to 48 hours to propagate.
- Use tools like `dnschecker.org` to verify record updates globally.

### Confirmation in GitHub
- Once DNS is correctly set up, GitHub will display the custom domain.
- Test the URL to confirm it's serving your GitHub Pages content.

---

## Using Subdomains and Redirects

### Redirecting Apex to www
Use domain forwarding or ALIAS/ANAME records (if supported by your registrar) to redirect example.com → www.example.com.

### Adding Subpages or Docs
Link multiple subdomains to different GitHub repositories:
- blog.example.com → blog repository
- docs.example.com → documentation site

---

## Securing and Optimizing Your GitHub Hosting Setup

### SEO and Metadata
- Add meta tags in HTML or use Jekyll’s `_config.yml` to define site metadata.
- Customize `robots.txt` and `sitemap.xml` for search engines.

### Performance Tips
- Minify CSS and JavaScript
- Use responsive images
- Enable caching with proper headers in static files

### Analytics Integration
- Add Google Analytics or Plausible script in your HTML or Jekyll layout

---

## Common Issues and Troubleshooting

### Problem: Site Not Showing Up
- Double-check DNS settings
- Ensure CNAME file matches DNS subdomain
- Wait for DNS propagation

### Problem: HTTPS Not Available
- Ensure domain resolves correctly
- GitHub can take a few hours to provision SSL

### Problem: Wrong Repository
- Verify GitHub Pages is enabled in the correct repository and branch

---

## Advanced Configurations

### Custom 404 Page
- Add `404.html` to the root to override default GitHub 404 page

### Using Jekyll Themes
- Add `remote_theme:` in `_config.yml`
- Customize layouts using Liquid templates

### GitHub Actions for Deployment
- Automate page builds using GitHub Actions CI/CD workflows

---

## Migrating Domains or Projects

### Changing Domains
- Update DNS records and CNAME file
- Allow time for propagation

### Moving Repositories
- GitHub Pages URL will change if repo name changes (unless custom domain used)

---

## Final Thoughts

Using a custom domain with GitHub hosting elevates your web presence and establishes a professional identity. With this step-by-step guide, you can easily connect your domain, ensure HTTPS security, and build a fast, reliable site using GitHub Pages. Whether you're a developer, designer, student, or entrepreneur, mastering custom domains on GitHub opens the door to elegant, scalable web publishing.

---

## Related Posts
- [How to Deploy a Jekyll Blog with GitHub Pages](https://yourblog.com/jekyll-github-pages-guide)
- [Best Free Hosting Options for Static Sites](https://yourblog.com/free-static-site-hosting)
- [GitHub Actions for Website Automation](https://yourblog.com/github-actions-web)

