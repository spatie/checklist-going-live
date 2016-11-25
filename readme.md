# A checklist for all projects that are going live

This checklist is used whenever a site is going live at https://spatie.be

## 1. Browserstack tests
- [ ] Desktop: test on latest versions of Chrome, IE/Edge, Firefox, Safari
- [ ] Mobile: test on latests versions of Mobile Safari, Android

## 2. Front-end checklist
- [ ] Does Favicon load? Pin the tab in Safari to check icon
- [ ] Search sources for `http://`. Replace by `https://`
- [ ] Run `csscomb` on `scss` assets
- [ ] Check JS lint errors. Remove all `console.log` lines in scripts
- [ ] Webfonts: is the live domain configured in services like Typekit, Fonts.com etc.?
- [ ] Are 404, 500 en 503 pages provided? Do they provide useful content like 'back to home', search or a navigation tree?
- [ ] Test Facebook sharing. Provide og-tags if needed
- [ ] Is `yarn.lock` present?
- [ ] Only jQuery v3 may be used. All references to jQuery 2 must be removed `npm ls jquery`
- [ ] Check total weight of homepage

## 3. Check content (with an open console)
- [ ] Are all strings / images present?
- [ ] Does the menu has a correct active state on every page?
- [ ] Check page titles / descriptions
- [ ] Check for console errors
- [ ] Check all pages for n+1 problems?

Repeat this section for all languages

### Components
- [ ] Google Maps
    - [ ] API key needed/configured?
    - [ ] Check info windows
    - [ ] Prevent zoom out beyond 1x world
    - [ ] Try clicking on markers
- [ ] Forms: fill out with wrong/right values
- [ ] Video: check with sound on
- [ ] Try subscribing to a newsletter
- [ ] Check layout of emails
- [ ] Check structured data for news, events, products, ...

## 4. Pre live
- [ ] Add redirects from old to new pages if necessary.

## 3. Post live
- [ ] Install Let's Encrypt certificate
- [ ] Check SSL certificate health https://www.ssllabs.com/ssltest/
- [ ] Check your hostfile to make sure you're looking at the live site
- [ ] Try visiting `www` domain, should redirect to `non-www`
- [ ] Try out visiting `http`, should redirect to `https`
- [ ] Verify that all http status codes are ok with https://github.com/spatie/http-status-check
- [ ] Scan for mixed content with https://github.com/bramus/mixed-content-scan
- [ ] Verify that the content of robots header is current with `curl -I https://url` om `x-robots-tag`
- [ ] Remove development DNS record
- [ ] Check dns propagation with https://www.whatsmydns.net/
- [ ] Verify Tag manager / analytics have been correctly set up

### Google Search Console
- [ ] Submit all www/non-www http/https variations
- [ ] Set up preferred domain domain to non-www https
- [ ] Crawl > Fetch as Google > Submit to index to kickstart index

### Back end
- [ ] Open up `/blender`
- [ ] Try the password reset flow
- [ ] Try saving article / news / ...
- [ ] Verify all e-mail recipients are correct

### Server
- [ ] Are Backups Digital Ocean enabled?
- [ ] Are Amazon backups enabled?
- [ ] Is New Relic licentie server monitoring been set up?
- [ ] Is the output of artisan task `backup:run` ok?
- [ ] Is the frequently job configured on Forge?
- [ ] Are the queues set up on Forge? ('default' and 'media_queue')?

## About Spatie
Spatie is a webdesign agency based in Antwerp, Belgium. You'll find an overview of all our open source projects [on our website](https://spatie.be/opensource).
