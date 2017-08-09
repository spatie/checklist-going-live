# A checklist for all projects that are going live

This checklist is used whenever a project is going live at https://spatie.be

## 1. Browserstack tests
- [ ] Desktop: test on latest versions of Chrome, IE/Edge, Firefox, Safari
- [ ] Mobile: test on latest versions of Mobile Safari, Android

## 2. Front end checklist

### Assets
- [ ] Search sources for `http://`. Replace by `https://`
- [ ] Lint (s)css sources
- [ ] Webfonts: is the live domain configured in services like Typekit, Fonts.com etc.?
- [ ] Is the browserlist properly configured for autoprefixer and babel-preset-env?

### Scripts
- [ ] Only jQuery v3 may be used. All references to jQuery 2 must be removed `npm ls jquery`
- [ ] Is `yarn.lock` present?
- [ ] Check JS lint errors. Remove all `console.log` lines in scripts
- [ ] Check for console errors

### Page weight
- [ ] Evaluate total weight of at least homepage
- [ ] Open Inspector network/timeline tab to identify heavy assets 
- [ ] Check if heavy assets are cached 

### Performance
- [ ] Use the Chrome DevTools and throttle your CPU and network with 10x CPU slowdown and set the network to "Good 3G".

## 3. Check content (with an open console)
- [ ] Are all strings / images present (and translated)?
- [ ] Does menu/submenu have a correct active state on every page?
- [ ] Are 404, 500 and 503 pages provided? Do they provide useful content like 'back to home', search or a navigation tree?
- [ ] Check all pages for n+1 problems

### Meta
- [ ] Check page titles / descriptions
- [ ] Test Facebook sharing. Provide og-tags if needed
- [ ] Does Favicon load? Pin the tab in Safari to check pinned icon

_Repeat this section for all languages_

### Components
- [ ] Google Maps
    - [ ] API key needed/configured?
    - [ ] Check info windows
    - [ ] Prevent zoom out beyond 1x world
    - [ ] Try clicking on markers
- [ ] Forms: fill out with wrong/right values
- [ ] Video: check with sound on
- [ ] Try subscribing to a newsletter with incorrect & correct email (use correct mail twice to get 'already subscribed' message)
- [ ] Check layout of emails
- [ ] Check structured data for news, events, products,... https://search.google.com/structured-data/testing-tool/

## 4. Back end checklist
- [ ] Open up `/blender`
- [ ] Remove unused modules from main menu 
- [ ] Configure Analytics dashboard
- [ ] Create a new admin and try to log in
- [ ] Try the password reset flow for existing user
- [ ] Try saving article / news / ...
- [ ] Verify all e-mail recipients are correct
- [ ] Check client's logo in header

## 5. Server, DNS & Services
- [ ] Add redirects from old to new pages if necessary.
- [ ] Install Let's Encrypt certificate
- [ ] Check SSL certificate health https://www.ssllabs.com/ssltest/
- [ ] Check your hostfile to make sure you're looking at the live site
- [ ] Try visiting `www` domain, should redirect to `non-www`
- [ ] Try out visiting `http`, should redirect to `https`
- [ ] Verify that all http status codes are ok with https://github.com/spatie/http-status-check
- [ ] Scan for mixed content with https://github.com/spatie/mixed-content-scanner-cli
- [ ] Verify that the content of robots header is current with `curl -I https://url` on `x-robots-tag`
- [ ] Remove development DNS record
- [ ] Check dns propagation with https://www.whatsmydns.net/
- [ ] Verify Tag Manager / Analytics have been correctly set up

### Google Search Console
- [ ] Submit all www/non-www http/https variations
- [ ] Set up non-www https as the preferred domain 
- [ ] Crawl > Fetch as Google > Submit to index to kickstart index

### Server
- [ ] Are Digital Ocean backups enabled?
- [ ] Are Amazon backups enabled?
- [ ] Is the output of artisan task `backup:run` ok?
- [ ] Is artisan scheduled on Forge?
- [ ] Are the queues set up on Forge? ('default' and 'media_queue')? Do they have a low max return limit?
- [ ] Is the url being monitored by our uptime-monitor?
- [ ] Is the server being monitored by our server-monitor?

### Github
- [ ] Remove `develop` branch or other stale branches 

## About Spatie
Spatie is a webdesign agency based in Antwerp, Belgium. You'll find an overview of all our open source projects [on our website](https://spatie.be/opensource).
