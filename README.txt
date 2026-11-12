ADITYA GUPTA PORTFOLIO SITE: HOW TO EDIT, HOST AND GET IT ON GOOGLE
===================================================================

What is in this folder
  index.html        the whole site (text, layout, styles, script)
  img/              every photo
  video/            every video clip
  og-image.jpg      the preview card shown when the link is shared on LinkedIn or WhatsApp
  favicon.svg, favicon-48.png, apple-touch-icon.png, icon-512.png   browser and phone icons
  robots.txt, sitemap.xml   files that help Google find the site
  .nojekyll         tells GitHub Pages to serve the files as they are (keep it)
  README.txt        this file

You do not need Google Drive, Claude, or any special software.
The site is plain files. Edit them on your computer, then upload them.


1. PREVIEW ON YOUR COMPUTER
  Double-click index.html. It opens in your browser.
  After any change: save the file, then refresh the browser tab.


2. EDIT TEXT
  Open index.html in a text editor (VS Code is free and the easiest; Notepad works).
  Press Ctrl+F, search for the words you want to change, type over them, save.


3. ADD A PHOTO OR VIDEO TO A PROJECT
  a. Copy the file into img/ (photos) or video/ (clips).
     Use simple names: lowercase, hyphens, no spaces.  e.g. leg-drop-test.jpg
  b. In index.html find the project (search for its title). Under it is a block:

        <div class="gallery" ...>
            <img src="img/leg-on-table.jpg" alt="..." data-tag="Hardware" ...>
            <video src="video/leg-rail-test.mp4" poster="img/leg-rail-test-poster.jpg" ...></video>
        </div>

  c. Add ONE new line inside that block.

     Photo:
        <img src="img/leg-drop-test.jpg" alt="Leg mid-drop on the rail" data-tag="Test">

     Video:
        <video src="video/leg-jump.mp4" poster="img/leg-jump-poster.jpg" data-tag="Test" data-caption="Leg jumping" muted playsinline preload="none"></video>

     alt / data-caption  = the caption shown under the slide (Google also reads it)
     data-tag            = the amber label: CAD, Hardware, Test, Flight, or anything short
     poster              = a still image shown before the video plays (a screenshot of the clip)

  The order of the lines is the order they slide in.
  Delete a line to remove that slide. Photos stay up 4.5 seconds; videos play to the end.


4. SWAP A PHOTO (same place, new picture)
  Replace the file in img/ and keep the exact same file name. No code change.
  Headshot: img/aditya-portrait.jpg      Cover: img/mumbai-skyline.jpg


5. LINKS (resume, portfolio, LinkedIn, email)
  Near the bottom of index.html find:   const LINKS = {
  Paste the new link between the quotes. Google Drive links must be shared as
  "Anyone with the link can view", or visitors will see an access request.


6. ADD A NEW PROJECT
  Copy one whole block from   <article class="proj" ...>   to   </article>
  Paste it where you want it in the order, then change:
    id="..."           a unique short name (no spaces)
    data-cat="..."     which filter chips show it: iitb robotics mech aircraft multirotor
    the gallery lines, the title, the text and the spec rows.


7. KEEP FILES SMALL (the site loads faster and ranks better)
  Photos: under about 400 KB each, 1600 px on the long side. squoosh.app does this free in the browser.
  Videos: under about 5 MB each, 720p, no sound needed. HandBrake (free), preset "Fast 720p30".
  Phone clips straight from the camera are 20 to 50 MB each. Always compress them first.
  GitHub refuses single files over 100 MB.


8. PUT IT ONLINE WITH GITHUB PAGES (free)
  a. Make a free account at github.com. Pick your username carefully; it becomes your address.
  b. Click "New repository". Name it exactly:   yourusername.github.io
     Set it to Public. Create it.
  c. Click "uploading an existing file". Drag in EVERYTHING inside this folder
     (index.html, img, video, the icons, robots.txt, sitemap.xml, .nojekyll).
     If the browser skips the hidden .nojekyll file, use GitHub Desktop (free) instead.
     Click "Commit changes".
  d. Settings > Pages > Source: "Deploy from a branch", branch "main", folder "/ (root)". Save.
  e. After a minute or two the site is live at   https://yourusername.github.io
  To update later: upload the changed files again (same names overwrite the old ones).

  Optional but recommended: your own domain (about Rs 800 to 1,200 a year, e.g. adityagupta.in).
  Buy it, then in GitHub Settings > Pages > Custom domain type it, follow GitHub's DNS steps,
  and tick "Enforce HTTPS". A name-based domain looks more professional and is easier to share.


9. TELL GOOGLE ABOUT IT
  a. Replace YOUR-SITE-URL everywhere with your real address (no trailing slash), e.g.
     https://yourusername.github.io
     It appears in index.html, robots.txt and sitemap.xml. Use Ctrl+H (find and replace).
  b. In index.html, remove the comment markers  <!--  and  -->  around the "canonical" line.
  c. Go to search.google.com/search-console, click "Add property", choose "URL prefix",
     enter your address. Choose the "HTML tag" verification method, copy the code it gives you,
     paste it into the "google-site-verification" line near the top of index.html, remove that
     line's comment markers, upload index.html again, then click Verify.
  d. In Search Console: Sitemaps > enter  sitemap.xml  > Submit.
     Then URL Inspection > paste your address > "Request indexing".
  e. Link to the site from everywhere you already exist: LinkedIn (Contact info > Website, and
     the Featured section), your resume header, your GitHub profile, and Google Scholar or ORCID
     if you set those up. Links from your own profiles are what tie the site to your name.
  Google usually picks a new site up within a few days to two weeks.


10. HOW TO CHECK IT IS WORKING
  Search Google for:   site:yourusername.github.io
  If the page shows up, it is indexed. Then try searches like
  "Aditya Gupta IIT Bombay mechanical" and watch Search Console > Performance.
