# Terraform Cert Trainer 1.0.1 — English edition
Unofficial study MVP for HashiCorp Terraform Associate (004), Terraform 1.12.

## Changes in 1.0.1
- English-only interface, lessons, answer explanations, feedback, settings and documentation.
- English date formatting and page/manifest language metadata.
- Updated service worker cache version. No changes to question IDs, level IDs, scoring, or the progress schema.

## Running locally or on GitHub Pages
Extract the ZIP into your repository root and upload all files. Select Settings → Pages → Deploy from a branch → main → / (root). For local use, run `python3 -m http.server 8000` in the extracted directory and open http://localhost:8000. Do not use file://. No backend or cloud deployment is required.

## Updating from 1.0
1. Export your progress using Backup → Export JSON before updating.
2. Replace all application files in the existing repository, keeping the same web origin. The IndexedDB name `tf-cert-trainer`, store `progress`, key `current`, schema and all IDs remain unchanged.
3. Commit the files and allow GitHub Pages to deploy. Reload with Ctrl+F5. If necessary, close other application tabs and reopen the page online to allow the new service worker to activate.
4. Verify your progress. If you changed the origin or lost local data, import your exported backup. Import replaces progress; it does not replace study content. Reset progress preserves study content; resetting the local database also clears the offline cache.

## Features
- 8 domains, 37 objectives, 37 lesson levels and 11 review levels, 185 concepts and 601 exercises including variants.
- 15 questions per level, 12/15 passing threshold, explanations, mistake review, sequential unlocking and history.
- Unrestricted practice with domain, objective, type, difficulty and incorrect-answer filters. If fewer questions are available than requested, the available unique questions are used.
- Single choice, multiple answer, true/false, exact fill-in and ordering. Fill-in compares exact text after whitespace normalization; synonyms are not recognized.
- IndexedDB, JSON backup/import, PWA manifest and offline caching after successful initial loading. Offline support depends on the browser; external documentation requires internet access.
- Consolidated concepts require correct latest answers to at least two distinct questions and no currently incorrect answers. This is not proof of long-term retention.

## Sources
- https://developer.hashicorp.com/certifications/terraform-associate
- https://developer.hashicorp.com/terraform/tutorials/certification-004/associate-review-004
- https://developer.hashicorp.com/terraform/tutorials/certification-004/associate-study-004

Questions are original practice variants, not exam dumps. Documentation links are topical and have not been individually verified for every question. HCL examples are illustrative snippets, not actual Terraform CLI execution results.

## Verification and limitations
Version 1.0.1: JavaScript syntax, JSON parsing, unchanged question answers and IDs, unchanged level/concept IDs and storage identifiers, and absence of Slovak accented characters in application text checked. Browser interactions, IndexedDB persistence and service worker activation have not been tested end-to-end for this release. No full technical audit of the question bank has been performed. Adaptive review, daily tasks, achievements, exam simulation, dedicated CLI/HCL trainers and labs remain planned for future releases.
