# A checklist for all projects that are going live

This checklist is used whenever a site is going live at https://spatie.be

## 1. Browserstack tests
- [ ] desktop: test on latest versions of Chrome, IE/Edge, Firefox, Safari
- [ ] mobiel: test on latests versions of Mobile Safari, Android

## 2. Front-end checklist
- [ ] Does Favicon load?
- [ ] Search sources for `http://. Replace by `https://`
- [ ] Remove all `console.log`'s in scripts
- [ ] Webfonts: is the live domain configured in typekit?.
- [ ] Are 404, 500 en 503 pages provided. Do they contain good content like 'back to home', search or a navigation tree?
- [ ] Test Facebook sharing / provide og-tags
- [ ] Is Yarn.lock present?
- [ ] Only jQuery v3 maybe used. All references to jQuery 2 most be removed `npm ls jquery`

## 3. Check content (with an open console)
- [ ] Are all strings / images present?
- [ ] Does the menu has a correct active state on every page?
- [ ] Check for console errors
- [ ] Check total weight of homepage
- [ ] Check all pages for n+1 problems?

Repeat this section for all languages

### Components
- [ ] Google Maps
    - [ ] Check info windows
    - [ ] Check zoom out, should maximum be 1x world
    - [ ] Try clicking on markers
- [ ] Forms: full out with wrong/right values
- [ ] Video: check with sound
- [ ] Try subscribing to the newsletter
- [ ] Check layout of mails
- [ ] Check structured data voor news, events, products, ...

## 4. Pre live
- [ ] Add redirects from old to new pages if necessary.

## 3. Post live
- [ ] Install Let's Encrypt certificate
- [ ] Check ssl certificate health https://www.ssllabs.com/ssltest/
- [ ] Check your hostfile to make sure you're looking at the live site
- [ ] Try visiting  `www` domain, should redirect to `non-www`
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
- [ ] Crawl > Fetchen as Google > Submit to index

### Back end
- [ ] open up `/blender`
- [ ] Try the password reset flow
- [ ] Try saving article / news / ...
- [ ] Verify all e-mail recipients are correct

### Server
- [ ] are Backups Digital Ocean enabled?
- [ ] are Amazon backups enabled?
- [ ] is New Relic licentie server monitoring been set up?
- [ ] is the output of artisan task backup:run ok?
- [ ] is the frequently job configured on forge??
- [ ] are the queues set up on Forge? ('default' and 'media_queue')?
