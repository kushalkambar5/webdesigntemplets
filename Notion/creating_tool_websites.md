- Astro JS (SEO is best)
- Cloudfare for deployment

- Find a problem
- Search on google existing compitators
- visit all websites
- list out all features and their down points and new features
- ahrefs.com/keyword-generator
    - Phrase match - for keywords
    - Questions - for FAQ’s
    - “People also ask” from google
    - Also keywords can be find by google search
- Target mainly USA
- To find domains - https://instantdomainsearch.com/
- .com domain only
- Domains: (compare prices here)
    - namecheap.com
    - godaddy
    - bigrock
    - hostinger
- Skills:
    - Vercel design md - npx getdesign@latest add vercel
    - vercel web-design-guidelines skill - npx skills add vercel-labs/agent-skills --skill web-design-guidelines
    - tailwind-agent-skill skill - https://github.com/Lombiq/Tailwind-Agent-Skills - npx skills add Lombiq/Tailwind-Agent-Skills
    - AstroJS skill - npx skills add https://github.com/delineas/astro-framework-agents --skill astro-framework
    - AstroJS docs MCP
- Create website and fix the errors
- add Dark-Light toggle
- add responsiveness for mobile and etc users
- Website should be MPA(Multi Page Application) (SEO will be good)
- Favicon
    - shipfa.st/tools/logo-fast
    - realfavicongenerator.net - download and unzip the file and copy those files in frontend/public/ and also add the code of it which is given by the website
- If hosted on cloudfare then there will be one issue i.e. duplicate content/websites, now we have to disable the cloudfare domain website:
    - for cloudfare workers website we can disable it from cloudfare settings
    - but for cloudfare pages website we have to block the crawler by adding _headers file on that cloudfare pages website domain name
- also in package.json add deploy command to package.json, this will when we run the “npm run deploy” this will automatically deploy also on the online/live site
- submit website on google analytics and google search console and bing search

https://youtu.be/tDeLeyPvZn0?si=RmGl9k2yCsbOyAj7

# **CompileFuture Website Checklist ✅**

- create Website with Prompt (give competitor url)
- use (logofa.st) for the logo & favicon
- Add Favicon (use real favicon generator)
- website should be mobile responsive
- do SEO with prompt (write about the tool 600 words)
- add FAQ section
- add privacy policy, about us, terms & conditions, contact us pages and this website should be MPA - multi page application for best seo
- add error pages (404, 500)
- sitemap.xml
- robots.txt and mention sitemap link in it
- https://isitagentready.com/
- add google analytics code
- add _headers file for cloudflare pages / if using workers then disable workers.dev domains after connecting the .com domain

# **Website Creation Prompt**

```
I have initialized a new astrojs project, use astro docs mcp and tailwind-4-docs & web-design-guidelines skills for creating the website. Also use @DESIGN.md file and keep the website design like vercel.

Name: Real Online Ruler
Domain: realonlineruler.com

Create an online ruler website that will have ruler on the edges, user can select where to place the ruler. we want these 3 calibration methods
Method 1: Auto-Detect Device
Method 2: Screen Diagonal
Method 3: Credit Card Calibration

My competitor website is https://anruler.com/ and it have some features which we need and we need to make a website better than it. Give me ideas how to make it better. go on to this website and check what exactly we need to make. Do not copy design or ui from that website.
```

# **SEO Prompt**

```
Do the On Page SEO of this Website for

Main Keyword: Online Ruler
Supporting Keywords: online ruler inches, online ruler in cm, online ruler mm, online ruler cm, free online ruler, online ruler in mm, online ruler camera, mm online ruler, accurate online ruler, 12 inch online ruler, online ruler inches actual size, online ruler to scale, online ruler 12 inch, online ruler tool, online ruler actual size, real online ruler, actual size online ruler

these above keywords, also use proper og meta tags for SEO
on home page write 600 words about the tool for SEO
```

# **FAQ Section Prompt**

```
add seo friendly FAQ section for these below questions:

Can I use my phone as a ruler?
Is there a ruler online?
How to identify 1 inch?
How to measure cm online?
Can a smart phone measure?
Can I use my camera as a ruler?
Can we measure online?
how to read a ruler online
how to view ruler in word online
how to add a ruler in word online
how to show ruler in powerpoint online
how to use online ruler
how to add ruler in word online
how to use a ruler online

NOTE: Use JSON-LD for FAQ SEO
example: ```
 <script type="application/ld+json">
 {
 "@context": "https://schema.org",
 "@type": "FAQPage",
 "mainEntity": [{
 "@type": "Question",
 "name": "How to find an apprenticeship?",
 "acceptedAnswer": {
 "@type": "Answer",
 "text": "<p>We provide an official service to search through available apprenticeships. To get started, create an account here, specify the desired region, and your preferences. You will be able to search through all officially registered open apprenticeships.</p>"
 }
 }, {
 "@type": "Question",
 "name": "Whom to contact?",
 "acceptedAnswer": {
 "@type": "Answer",
 "text": "You can contact the apprenticeship office through our official phone hotline above, or with the web-form below. We generally respond to written requests within 7-10 days."
 }
 }]
 }
 </script>
```
```

# **_headers file**

```
https://project.pages.dev/*
  X-Robots-Tag: noindex
```

# **Links:**

- Logo & Favicon: https://logofa.st/
- Ahrefs Keyword Generator: https://ahrefs.com/keyword-generator
- Domain Search: https://instantdomainsearch.com/
- Vercel Design MD: https://getdesign.md/vercel/design-md – npx getdesign@latest add vercel
- Web design guidelines skill: https://www.skills.sh/vercel-labs/agent-skills/web-design-guidelines
- Tailwind v4 Docs: https://www.skills.sh/lombiq/tailwind-agent-skills/tailwind-4-docs or https://github.com/Lombiq/Tailwind-Agent-Skills
- AtroJS Docs: https://docs.astro.build/en/getting-started/
- Google Analytics: https://analytics.google.com
- AstroJS Cloudflare Deploy: https://docs.astro.build/en/guides/deploy/cloudflare/
- AstroJS MCP Server: https://docs.astro.build/en/guides/build-with-ai/#astro-docs-mcp-server
- Cloudflare: https://dash.cloudflare.com/login
- Google Search Console: https://search.google.com/search-console/about
- Bing Webmaster: https://www.bing.com/webmasters/about
- Google Adsense: https://adsense.google.com/start/