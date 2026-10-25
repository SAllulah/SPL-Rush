SPL Pipe Rush — offline / on-prem copy
======================================

This folder is a complete, self-contained copy of the SPL Pipe Rush trainer.
It makes NO connection to the internet. Nothing phones home: no fonts, no
analytics, no update checks, no CDN, no telemetry. Everything it needs —
the app, the narration audio, the icon — is inside this folder and is loaded
with relative paths, so it runs from any location and any static web server.

(The only web addresses anywhere in the app are inside lesson text, e.g. an
example Splunk workflow-action URL and a link to Splunk's exam blueprint.
They are shown as text for learning; the app never requests them.)


WHAT'S IN HERE
--------------
  index.html            the whole app (open this)
  audio/pack00.mp3 …    narration, bundled into ~379 pack files (used when hosted)
  audio/clips/*.mp3     the same narration as one file per clip (used on file://)
  README.txt            this file

Two copies of the audio are included on purpose. When the app is hosted over
http/https it streams the packs (fewer, larger files). When you open it from
the local filesystem (file://) browsers cannot read the packs, so it plays the
per-clip files instead. You do not have to choose — the app detects which to use.


OPTION 1 — JUST OPEN IT (air-gapped laptop, no server)
------------------------------------------------------
Double-click index.html, or drag it into Edge or Chrome. It runs from file://.
Narration plays the per-clip files in audio/clips/. Your progress is saved in
that browser (localStorage). This is the simplest way and needs no setup.

Notes:
  • Use Edge or Chrome.
  • Keep the folder together — index.html, audio/ and audio/clips/ must stay
    side by side.
  • The first tap anywhere turns on sound (browsers require one tap before any
    audio). If you ever see a "Tap to enable sound" chip, tap it.


OPTION 2 — HOST IT ON A STATIC SERVER (shared, intranet)
--------------------------------------------------------
Copy this whole folder to any static web server. It works at the site root or
under any sub-path, on IIS, nginx, Apache, or Python — paths are all relative.

  Python (quick test):      python3 -m http.server 8080
                            then open http://localhost:8080/

  nginx / Apache:           drop the folder in the web root. No config needed.

  IIS:                      make sure these MIME types are registered (IIS does
                            not serve unknown extensions by default):
                                .mp3   -> audio/mpeg
                                .woff2 -> font/woff2   (only if you add fonts later)
                            index.html, .html and .css are served by default.
                            Add the .mp3 mapping under the site's MIME Types, or
                            in web.config:
                                <staticContent>
                                  <mimeMap fileExtension=".mp3" mimeType="audio/mpeg" />
                                </staticContent>

When hosted, narration uses the packs and is cached per clip. Progress saves to
the browser (localStorage); there is no account or server storage in this copy.


REQUIREMENTS
------------
A recent Edge, Chrome, Firefox or Safari. No internet. No plugins. No install.


FONTS
-----
This offline copy uses the fonts already on your computer (a clean system-font
stack) so that it needs no downloads. The look is the same; only the exact
typeface differs slightly from the online version.
