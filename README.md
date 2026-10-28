[<img src="https://github.com/open-spaced-repetition/fsrs4anki/assets/32575846/9efb2ca5-51bd-411d-9694-a77b09f51fa7" align="left" width="64" height="64">](https://github.com/open-spaced-repetition/awesome-fsrs)

# Awesome FSRS [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A curated list of awesome FSRS implementations, papers and resources. Feel free to suggest new projects in Issues or PR directly.

## Implementation

- Python
  - Scheduler (v6) + Optimizer: [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs)
  - Scheduler (v5): [rs-fsrs-python](https://github.com/open-spaced-repetition/rs-fsrs-python)
  - Optimizer (v6): [fsrs-optimizer](https://github.com/open-spaced-repetition/fsrs-optimizer)
  - Optimizer (v6): [fsrs-rs-python](https://github.com/open-spaced-repetition/fsrs-rs-python)
  - [Deprecated] Optimizer: [fsrs-optimizer-tiny](https://github.com/open-spaced-repetition/fsrs-optimizer-tiny)
- Rust
  - Scheduler (v5): [rs-fsrs](https://github.com/open-spaced-repetition/rs-fsrs)
  - Scheduler (v6) + Optimizer: [fsrs-rs](https://github.com/open-spaced-repetition/fsrs-rs)
    - Run in browsers: [fsrs-browser](https://github.com/open-spaced-repetition/fsrs-browser)
- TypeScript
  - Scheduler (v6): [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs)
- Go
  - Scheduler (v5): [go-fsrs](https://github.com/open-spaced-repetition/go-fsrs)
- Java
  - Scheduler (v5): [rs-fsrs-java](https://github.com/open-spaced-repetition/rs-fsrs-java)
- Scala
  - Scheduler (v6): [fsrs4s](https://github.com/jwbargsten/fsrs4s)
- C
  - Scheduler (v5): [rs-fsrs-c](https://github.com/open-spaced-repetition/rs-fsrs-c)
- Nodejs
  - Scheduler (v5): [rs-fsrs-nodejs](https://github.com/open-spaced-repetition/rs-fsrs-nodejs)
- Dart
  - Scheduler (v4.5): [dart-fsrs](https://github.com/open-spaced-repetition/dart-fsrs)
- Swift
  - Scheduler (v5): [swift-fsrs](https://github.com/open-spaced-repetition/swift-fsrs)
- Clojure/ClojureScript
  - Scheduler (v4): [cljc-fsrs](https://github.com/open-spaced-repetition/cljc-fsrs)
- Ruby
  - Scheduler (v4): [rb-fsrs](https://github.com/open-spaced-repetition/rb-fsrs)
- Kotlin
  - Scheduler (v6): [FSRS-Kotlin](https://github.com/open-spaced-repetition/FSRS-Kotlin)
  - Scheduler (v4): [android-fsrs](https://github.com/open-spaced-repetition/android-fsrs)
- Elixir
  - Scheduler (v4): [ex_fsrs](https://github.com/open-spaced-repetition/ex_fsrs)
- OCaml
  - Scheduler (v5): [ocaml-fsrs](https://github.com/chaosarium/ocaml-fsrs)
- Lisp
  - Scheduler (v6): [lisp-fsrs](https://github.com/open-spaced-repetition/lisp-fsrs)
- Haskell
  - Scheduler (v7): [haskell-fsrs](https://github.com/kutyel/haskell-fsrs)

## Application

### General Flashcard

#### [Anki](https://apps.ankiweb.net/)

  Free and open source, content-agnostic flashcard application for Windows, Mac, Linux, iPhone, and Android. Supports text, images, audio, videos, and scientific markup (via LaTex). Offers free synchronization service using AnkiWeb, with community-shared add-ons and decks.

- FSRS available as an opt-in feature replacing the default SM-2 algorithm.
- Additionally, this [add-on](https://ankiweb.net/shared/info/759844606) offers a variety of extra features, such as Postpone, Advance, Load Balancing and Easy Days.

#### [Avorio](https://avorio.ai/)

  Avorio is a native flashcard app for macOS and iPhone built around FSRS-5. It imports Anki `.apkg` and `.colpkg` files with scheduling state, review history, media, tags, note types, cloze deletions and image occlusion cards intact, so decks resume on the schedule they were already on instead of resetting to new, and exports back to `.apkg`. Cards live in a local SQLite database and the review path makes no network calls, so it works offline and does not require an account. The flashcard app, FSRS-5, Anki import/export, local AI via Ollama, and offline mode are free; optional subscriptions add cloud AI generation and Mac-to-iPhone sync.

- FSRS-5 is the default scheduler. SM-2 is available per deck, and switching between them does not reset progress.
- On import, Avorio can fit FSRS parameters to your own Anki review log rather than using generic defaults.
- Avorio uses its own FSRS-5 implementation in a shared Rust core, exposed to SwiftUI through [UniFFI](https://github.com/mozilla/uniffi-rs).

#### [Azri](https://azri.app/)

  Azri (formerly Simple Anki) is a flashcard app for iPhone and iPad, free on the [App Store](https://apps.apple.com/app/apple-store/id1625870857?pt=124486958&ct=awesome-fsrs&mt=8). It makes cards from notes, photos and PDFs with AI, imports Anki `.apkg` decks and CSV files, and has an [MCP server](https://azri.app/mcp/) so Claude, ChatGPT and other AI apps can save cards to your decks. Reviews, manual cards and imports are free with no card limit; an optional Pro subscription adds cloud sync, unlimited AI generation, a web app and the MCP server.

- Uses [swift-fsrs](https://github.com/open-spaced-repetition/swift-fsrs) (FSRS-5) on iPhone and iPad. The web app uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) 4.7, also FSRS-5, with the same presets.
- Default FSRS-5 parameters. No optimizer runs, so the weights aren't fitted to your review history.
- Presets: Default (90% desired retention, 365-day maximum interval), Aggressive (95%, 90 days) and Relaxed (85%, 365 days). Custom sets desired retention from 80% to 99%, a maximum interval of 30, 90, 180 or 365 days, and turns fuzz and short-term scheduling on or off.
- Anki imports bring over the text of two fields per note as new cards. Review history and media aren't imported, so FSRS starts from your first review in Azri.
- Cards saved through the MCP server start in the FSRS new state, like cards made in the app.

#### [Discito](https://discito.app)

  Discito is a native iOS flashcard app built around FSRS-6, with iCloud sync, on-device AI card generation, lecture-audio-to-flashcards, image occlusion authoring, and full-fidelity `.apkg` import/export. One-time purchase, no subscription.

  Discito uses its own Swift FSRS-6 port (validated for parity against [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs)), with the parameter optimizer bridging [fsrs-rs](https://github.com/open-spaced-repetition/fsrs-rs) via swift-bridge FFI.

#### [Dushed](https://dushed.com/)

  Dushed is a web app that keeps your flashcards, notes, bookmarks, web feeds, Kindle highlights and files in one private library. A flashcard can refer to the note, web page, file or PDF page that it came from, and these references show during a review. Full-text search covers the whole library, including the text inside PDF files. A [demo](https://demo.dushed.com) is available without an account.

- Uses its own Go implementation of FSRS.
- Three ratings: Forgot, Good and Easy. Each rating shows the next due date before you select it.
- Imports Anki decks or CSV files. You can export flashcards as CSV or `.tar` at any time.
- The rest of the library:
  - Notes in Markdown, with images, code and attached files.
  - Kindle highlights and notes, imported from the Kindle notebook.
  - Web feeds (RSS, Atom and JSON Feed), with OPML import and export.
  - Bookmarks, with browser HTML and CSV import and export.
  - Files of any type; images, PDF, audio and video open in the browser.
- Flashcards need the Pro plan ($12/month). But there's a generous 30-day trial with no credit card required. Bookmarks are free up to 10,000.

#### [Etude](https://zibhelina.github.io/etude/)

  Etude is a free, open-source (MIT), self-hosted flashcard app where every card type is a small program. A card can generate fresh numbers to compute on every review, ask you to find the checkmate on a real board, play a chord on a piano, drag events onto a timeline, or draw a diagram; open answers can be graded by AI (your own API key, a local endpoint, or Sign in with ChatGPT), or not at all. It runs in the browser on desktop and phones (with a one-click Mac app), stores everything in a local SQLite database, and every action is also a CLI command with JSON output, so an AI agent can build and manage your decks. Source on [GitHub](https://github.com/Zibhelina/etude).

- Uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) for FSRS-6 scheduling, with learning steps, fuzz and per-deck retention, limits and weights.
- A deck can have an exam deadline: no card is scheduled past it, and cards you already know get one last review before it.
- Imports Anki `.apkg` and `.colpkg` files with review history and media.

#### [Flipnem](https://flipnem.com/)

An Anki compatible online Flashcard platform that supports PWA install.

- Mnemonics, Deck Encryption, Deck Sharing, and an optional public profile to show off your progress
- An MCP server that allows user to connect their own AI agent to their collections for quizzing, deck management, and mnemonic reinforcement.
- Free and paid tiers
- FSRS scheduled flashcard reviews that rely on [rs-fsrs](https://github.com/open-spaced-repetition/rs-fsrs)

#### [Loudwalk](https://loudwalk.com)

  Loudwalk is a native iPhone and Mac flashcard app that asks your cards out loud: it speaks the day's due cards, listens to your spoken answer, grades it against the answer written on the card, and schedules it. It imports Anki `.apkg` and `.colpkg` files with media, review history and each deck preset's FSRS parameters, so the queue is the one you left, and the Mac app writes a `.colpkg` or an `.apkg` to go back. Reviewing on screen is free; the voice tutor is a subscription.

- FSRS-6, with the parameters and desired retention of each Anki deck preset; 17- and 19-value sets left by FSRS-4.5 and FSRS-5 are read the way Anki reads them. No optimizer runs in the app.
- The memory model is a Swift port of [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs). Around it, the rules of Anki's v3 scheduler (learning steps, fuzz, daily limits, queue order) are held on every build to answers recorded from Anki itself: 750 answer transitions, 2,862 fuzz draws and 8 queue snapshots replay identically.

#### [Markji](https://www.markji.com/)

  Markji is a flashcard application designed to help users efficiently memorize and retain information. It's particularly popular for language learning, exam preparation, and other memorization-heavy subjects. The app is developed by MaiMemo Inc., the company also behind the popular language-learning APP in China, [MaiMemo](https://www.maimemo.com/).

- Markji uses the MMX algorithm, a variant of FSRS developed by the same creator.

#### [Mochi Cards](https://mochi.cards/)

  **Mochi Cards** is a modern, Markdown-powered flashcard app available on Web, Desktop (Windows/macOS/Linux), and Mobile (iOS/Android).  

- Use **Markdown** to create flexible, multi-sided flashcards and notes  
- Create links between cards and notes, embed images/audio/video, cloze deletions  
- Study using **Spaced Repetition** and optional **FSRS algorithm** for smarter scheduling  
- Offline-first by default; sync securely across devices with a **Pro** subscription  
- Import Anki decks or export `.mochi` packages for backup and sharing

#### [MySummaries](https://mysummaries.app)

  MySummaries builds a spatial study board from a learner's own material — PDFs, slides, pasted text and photos of handwritten pages — and generates the review material from that board rather than from a shared deck. Alongside flashcards it writes timed written papers, audio lectures with word-level read-along, and a spoken oral examiner that asks follow-up questions over WebRTC and marks the transcript against a rubric. Web and iOS, free tier with usage-metered credits after that.

- Uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) for FSRS-6 scheduling with the default weights, across per-topic, per-subject and cross-subject due queues.
- `enable_short_term: false` — a lapsed card comes back within the same session through the drill queue rather than as a sub-day `due`.
- `enable_fuzz: true` and `maximum_interval: 365`, so a batch of cards generated together stops arriving together, and nothing is scheduled beyond a year.
- Questions missed in a written paper or an oral are turned back into cards automatically, deduplicated against the existing deck.

#### [Origa](https://github.com/yurvon-screamo/origa)

  Open source Japanese learning app for desktop (Windows, Linux, macOS) and Android. Built-in dictionaries, kanji, grammar, and phrases — all scheduled with FSRS. Russian and English. Offline-first.

- Uses [fsrs-rs](https://github.com/open-spaced-repetition/fsrs-rs) for FSRS-6 scheduling.

#### [Quanta](https://quanta-study.de)

  Quanta is an AI-powered flashcard and exam platform for German-speaking students (DACH region). It combines citation-first AI generation — where every card links to verifiable academic sources (Google Scholar, Wikipedia, textbooks) — with Bloom taxonomy control, LaTeX rendering, and MC quiz generation following Haladyna & Downing distractor guidelines.

- Quanta uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) for native FSRS-6 scheduling across all review modes (classic, endless, exam simulation).
- AI generates flashcards from topic, PDF, photo, or URL with mandatory source declaration before card creation (≥0.90 confidence threshold).
- Includes interactive Bloom taxonomy pyramid, Feynman method AI tutor, and 350+ German study programs with context-aware generation.
- Free tier includes FSRS-6 spaced repetition forever (50 AI cards/month). Pro €8/mo, Evo €14/mo with student discounts.

#### [Read Frog](https://www.readfrog.app/)

  Read Frog is an AI-powered language-learning platform centered on an open-source browser extension. It turns web pages and videos into an immersive study experience with bilingual page translation, streaming selection translation, context-aware explanations and article analysis, text-to-speech, and YouTube subtitle generation and translation—even for videos without captions. Users can bring their own models from more than 20 AI providers or use Read Frog's built-in AI.

- Custom AI Actions turn selected text into reusable tools for dictionaries, explanations, rewriting, and other workflows; their structured results can be mapped directly into Notebase.
- Vocabulary, definitions, example sentences, translations, and reading notes can be saved without leaving the current page, then converted into flashcards with customizable templates.
- A sync engine keeps cards, review logs, and scheduling state synchronized across devices and renders review sessions from live synchronized data.
- Its end-to-end spaced-repetition system uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) with the FSRS-6 model, middleware-based scheduling, and policy-driven review queues. A per-Notebase optimizer personalizes scheduling from review history.
- See [pricing](https://www.readfrog.app/pricing) and the public [roadmap](https://feedback.readfrog.app/roadmap).
- The [GPLv3-licensed browser extension](https://github.com/mengxi-ream/read-frog) is available for Chrome, Edge, and Firefox.

#### [Rember](https://www.rember.com/)

  A simple yet powerful spaced repetition system designed to help you remember more. It uses AI to automatically generate cards and FSRS-5 to schedule your reviews.

  Rember uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs).

#### [Revu](https://revu.cards/)

  Revu is a local-first spaced repetition app for macOS built with SwiftUI. It features a Notion-inspired interface, Anki import (.apkg/.colpkg), study guides, exams, and workload forecasting.

  Revu uses [swift-fsrs](https://github.com/open-spaced-repetition/swift-fsrs).

#### [SpacedCards](https://spacedcards.app)

  SpacedCards is an iOS flashcard app which forces students to review cards to unlock scrolltime. It works offline, is customizable & has AI for generating cards (images, audio or PDFs). 

  SpacedCards uses [dart-fsrs]([https://github.com/open-spaced-repetition/ts-fsrs](https://github.com/open-spaced-repetition/dart-fsrs)).
  

#### [spacedrep](https://github.com/wpwilson10/spacedrep)

  A CLI and MCP server for spaced repetition with .apkg import/export. Designed for scripting and AI agent workflows, no GUI required. Available on [PyPI](https://pypi.org/project/spacedrep/).

  spacedrep uses [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs).

#### [StudyDaily](https://www.studydaily.app/en)

  StudyDaily is a flashcard app for iPhone, iPad, Mac, Android, Windows and the web, built around FSRS-6. It imports Anki `.apkg` and `.colpkg` files with scheduling state, FSRS memory (stability and difficulty), deck presets, review history and media, so imported cards keep their due dates instead of resetting to new, and exports back to `.apkg`, `.colpkg` or CSV. A [published round-trip test](https://www.studydaily.app/en/guides/anki-to-studydaily-migration-test) moves a deck built with Anki 26.9.3 into StudyDaily and back, and compares every card and review log entry. Study, import and export work offline without an account; optional Premium adds sync between devices.

- Uses the official Dart package [fsrs](https://github.com/open-spaced-repetition/dart-fsrs) with the 21 FSRS-6 parameters; the rating buttons show the next interval before you answer.
- Imported Anki presets keep their desired retention, learning steps and FSRS parameters.
- Fuzz is applied with a seed derived from each review event, so replaying the review log on another device lands on the same due dates.

#### [Terminus](https://terminus-cards.pages.dev/?tag=awesome-fsrs)

  Terminus is a flashcard app for iPhone and iPad that you review from a Lock Screen and Home Screen widget. Free on the [App Store](https://apps.apple.com/app/id6822216429), no account.

- FSRS-6 (a Swift port of py-fsrs v6.3.2) is the only scheduler, with the default parameters.
- A set can have a test date: reviews are capped at halfway to the test so the gaps shrink as it gets closer, and the app shows readiness as the set's average predicted recall.

### Note-taking

#### [CuaderNote](https://cuadernote.com/)

  CuaderNote is a native notes and study app for Mac, iPhone and iPad. It combines a block editor, a PDF, EPUB and web article reader, and a freehand notebook with Apple Pencil support. Notes can be turned into flashcards, and highlights from PDFs and EPUBs go into the same review queue. Cards are stored on the device and sync through iCloud, so reviews work offline. The current version is free on the App Store, with no in-app purchases or subscriptions.

  - FSRS-6 with the default parameters and 90% desired retention. No optimizer runs in the app.
  - Uses its own Swift port of [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs), checked against py-fsrs's reference review vectors in its unit tests.

#### [Logseq](https://logseq.com/)

  A privacy-first, open-source platform for knowledge management and collaboration. It focuses on privacy, longevity, and user control.

  Logseq uses [cljc-fsrs](https://github.com/open-spaced-repetition/cljc-fsrs) in its database version.

#### [Obsidian](https://obsidian.md/)

  A personal notes, journaling, knowledge base, and project management application that allows the user to easily visualize relationships between information in graph form. Connect your notes via hyperlinks and install many community plugins made for Obsidian.

  - [obsidian-spaced-repetition-recall](https://github.com/open-spaced-repetition/obsidian-spaced-repetition-recall) is a modified version of obsidian-spaced-repetition and merging recall plugin to use seperate json data file. It uses FSRS-6.

  - [HiNote](https://github.com/CatMuse/HiNote) is a powerful Obsidian extension that helps you add comments to highlighted notes, use AI for thinking, and FSRS-6 for memory.

  - [LearnKit](https://github.com/ctrlaltwill/LearnKit) helps you remember what you write. It brings flashcards, note review, tests, and AI-assisted study tools into Obsidian, so your vault becomes a place to learn, not just store information. It uses FSRS-6 for spaced repetition scheduling.

  - [True Recall](https://github.com/pieralukasz/true-recall) is an Anki-like spaced repetition system for Obsidian on desktop, iOS and Android, with local-first SQLite storage, free cross-device sync, Anki import (including review history) and export, AI card generation, and detailed analytics. It uses FSRS-6 via [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs).

#### [Org-srs](https://github.com/bohonghuang/org-srs)

  Org-srs is a feature-rich and extensible spaced repetition system integrated with Org-mode, letting you learn and review without leaving Emacs.

  - Keeps review data and configuration in Org files, making sync and version control straightforward.
  - Bundles FSRS with parameter tuning, advanced scheduling features, and optional caching for large collections.
  - Extensible via hooks with embeddable entries, rich item types, charts, and touchscreen-friendly controls.

#### [Org-fc](https://github.com/l3kn/org-fc)

  Org-fc brings spaced repetition to Org-mode through flexible flashcard templates.

  - Marks Org headlines as cards with cloze, list, and custom layouts.
  - Includes experimental FSRS-6 scheduling powered by a Python helper.
  - Provides guides, migration tools, and mailing lists to support long-term study workflows.

#### [RemNote](https://www.remnote.com/)

  Multiplatform note-taking application with a simple and streamlined process of creating flashcards. Has an active community with student-made materials for exam preparation. Available for offline and online usage.

  RemNote integrated FSRS-4.5 into its scheduling system in [release 1.16](https://feedback.remnote.com/changelog/remnote-1-16-ultimate-spaced-repetition).

#### [SiYuan](https://github.com/siyuan-note/siyuan)

  SiYuan is a privacy-first, self-hosted, open source personal knowledge management system, written in TypeScript and Golang. It supports fine-grained block-level reference and markdown WYSIWYG.

  SiYuan's uses FSRS-5: [riff](https://github.com/siyuan-note/riff)

#### [TiddlyWiki](https://github.com/TiddlyWiki/TiddlyWiki5)

  TiddlyWiki is a customizable single HTML file personal wiki for creating interlinked notes. Its open-source nature and plugin ecosystem make it adaptable for various uses, from project management to knowledge systems. With the FSRS plugin, TiddlyWiki can also be used as a flashcard app for learning and memorization.

  FSRS is available as a fork of the Tidme plugin for TiddlyWiki: [fsrs4tw](https://github.com/open-spaced-repetition/fsrs4tw)

#### [ZKMemo](https://zkmemo.com)

  ZKMemo is a free, offline-first note-taking and learning software that combines FSRS-based spaced repetition with incremental reading. It features a SuperMemo-like interface, tree-structured knowledge management, AI integration, and Zettelkasten linking.
  
  - ZKMemo integrates FSRS-6, implemented using the [srs-everything](https://github.com/jiangege/srs-everything).
  - [Getting Started](https://help.zkmemo.com/getting-started.html)

### Incremental Reading

#### [Foliole](https://github.com/campfirium/foliole)

Foliole is an approachable incremental reading app for making reading actually complete.

Open source, open data, local first.

Native incremental reading with integrated FSRS scheduling, powered by [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs).

### Specialized Flashcard

#### [AI Japanese Tutor](https://www.aijapanesetutor.org)

**AI Japanese Tutor** blends voice-based Japanese verb conjugation practice with SRS-powered flashcards for JLPT N5 - N1 grammar and vocabulary.

- It uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) to schedule reviews of JLPT N5 - N1 vocabulary and grammar flashcards.
- Speech-based JLPT grammar flashcard reviews: translate English prompts into Japanese aloud, applying grammar points in context while reinforcing memory through speech.
- [Speech-based Japanese verb conjugation practice](https://www.youtube.com/watch?v=6ehilb5dzyc) with instant feedback to strengthen active recall of verb forms and speaking confidence.

#### [BiliMind Desktop](https://github.com/Odilient/bilimind-desktop)

BiliMind Desktop is an open-source (AGPL-3.0) app that turns a folder of lecture slides, past exam papers or notes into a course: lessons, quizzes checked against the source files, a study plan and an Anki-importable deck. Each course's review schedule is dated back from the exam and exported as an `.ics` calendar; the course page shows what is due today and reschedules locally as you answer.

- Uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) 5.4.2 with the default parameters (fuzz off, short-term steps on). One serialised FSRS state per item drives both the calendar export and the in-page "Due today" list.

#### [BrioVocab](https://briovocab.com)

BrioVocab is a French vocabulary app for CEFR A1–B2 learners, built around FSRS-6. It offers ready-made illustrated word sets for each level, plus the option to add your own words and phrases. Two study modes: Flip Cards (illustrated flashcards) and Super Coach (active recall exercises).

- FSRS-6 schedules reviews for every word; personalized parameters are recalculated from each learner's review history.
- Illustrated French vocabulary decks organized by CEFR level (A1, A2, B1, B2) — no deck building required.
- Suited for DELF A1–B2 prep and daily French vocabulary practice; an Anki alternative with pictures and ready-made French content.

Available on [App Store](https://apps.apple.com/app/id6793255945) and [Google Play](https://play.google.com/store/apps/details?id=com.briovocab.googleplay.app&referrer=awesome-fsrs).

#### [Chessbook](https://chessbook.com/)

  Mobile and web chess study application that combines multiple resources from YouTube, Lichess, ChessBase, and books to create a custom personal chess repertoire.

  Chessbook overhauled its spaced repetition system [using FSRS-4.5](https://x.com/chessbookcom/status/1805137108991946775).

#### [Gnoseed](https://gnoseed.com)

  Gnoseed is a web flashcard app (installable as a PWA) for engineers studying DevOps, AI&LLM, Cloud, Security and certification topics. It has more than 6,600+ ready-made multiple-choice cards in 70+ decks, plus open-answer interview decks. Free; it works offline and without an account, and an optional Google sign-in syncs progress across devices.

- Uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) with the FSRS-6 default weights and 90% desired retention; no per-user optimizer runs. FSRS is the default for new installs, SM-2 is selectable behind the same adapter, and switching resets scheduling state.
- No rating buttons in multiple-choice mode: a wrong answer is `Again`, a correct one is `Easy`, `Good` or `Hard` by answer time (4 s and 10 s by default, longer for scenario decks). In recall mode the options are hidden and the learner grades themselves: "I knew it" is `Good`, "I didn't know" is `Again`.
- [How Gnoseed schedules with FSRS](https://gnoseed.com/algorithms/fsrs), with an interval calculator.

#### [HSRS](https://github.com/satchelspencer/hsrs) 

Intended for language learning, HSRS continuously refreshes card content using a system of parameterized grammar cards. Individual reviews of a card reschedule all sub-cards in the parameter tree using bayesian statistics to estimate the contributions of each. Changes to stability from FSRS are interpolated in retrievability-space according to their probability. 

Used to power [grsly](https://grsly.com/), a tool for learning Japanese grammar.

#### [Japanese Learning](https://japanese-learning.ch)

Japanese Learning is a web course for German speakers preparing for JLPT N5: lessons on kana, vocabulary, kanji and grammar, explained in German, with a spaced-repetition review queue.

- Uses [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs) (FSRS-6) to schedule reviews of kana, kanji, vocabulary and grammar cards (default parameters, 90% desired retention, fuzzing on).
- Vocabulary also has a separate German-to-Japanese production queue, with its own FSRS state per card.
- Undo of the last rating, daily limits for new cards and reviews, and a listening mode (audio first, text hidden).
- Currently free, no ads. Reviews need a free account. German interface only.

#### [Jiaci (AI加词)](https://jiaci.app)

**Jiaci** is an open-source web app for Chinese speakers learning English vocabulary: pick a built-in word list (IELTS, TOEFL, GRE, CET, academic and everyday-life lists) or import your own, study a daily queue of cards, and rate each one *know* / *fuzzy*.

- Uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) to schedule reviews (no learning steps, day-level scheduling); a word whose scheduled interval reaches a configurable threshold is marked mastered.
- Word entries (core meaning, senses, examples, collocations, word family, mnemonics, etymology) are pre-generated offline by an LLM and shared by all users; server-side neural TTS for words, examples and definitions.
- Chinese UI only. [Source on GitHub](https://github.com/leoon-hu/jiaci) (MIT; Next.js + PostgreSQL).

#### [Jolito](https://github.com/smolkaj/jolito)

  Jolito is a calm, beautifully crafted Spanish vocabulary and grammar app designed as the antidote to clunky "tax-software" flashcards and bloated freemium gamification. It offers a distraction-free, tactile study experience with high-fidelity Mexican Spanish audio, seamless cross-device cloud sync, and zero recurring subscriptions or ads (free on the web, one-time purchase on mobile).

- **Simplicity Above All:** Fast, clutter-free practice sessions with fluid gestures, keyboard-first navigation, and zero cognitive overhead.
- **FSRS Memory Engine:** Uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) client-side to eliminate SM-2 ease decay on irregular grammar conjugations, with automatic bidirectional sibling burying.
- **Studio Audio & Spoken Recall:** High-fidelity neural pronunciation and speech evaluation, aggressively pre-cached for instant offline study.
- **Local-First & Multi-Device:** Instant cross-device cloud sync and lossless Anki `.apkg` imports, available on Web, iOS, and Android.

#### [KaChiKa](https://kachika.app/)

  KaChiKa is an AI-powered photo-to-flashcard app for language learners. Snap a photo of any object — a coffee cup, a cat, a street sign — and KaChiKa extracts the vocabulary, generates real-world example sentences, and schedules reviews using FSRS.

  Supports English, Japanese, French, Korean, Italian, Spanish, and Chinese. All photos are stored locally on device for privacy. Available on iOS, Android, and APK.

#### [LeetFlash](https://leetflash.com/)

  LeetFlash is a flashcard review app for review LeetCode algorithm questions. It leverages TS-FSRS for scheduling flashcards.

  The app consists of a Chrome extension, website for now. A mobile app is under development. It can automatically capture LeetCode question submissions and schedule your next review using an Anki-like experience. It supports both Leetcode and Leetcode China (力扣).

#### [Lexkite](https://lexkite.com/en/)

  Lexkite is a free web app (installable PWA) for learning English exam vocabulary for IELTS, TOEIC and TOEFL, with an interface in 15 languages. Reviews work offline and without an account. Decks can be exported to and imported from Anki `.apkg` files, optionally keeping each card's FSRS memory state.

  Lexkite uses its own JavaScript implementation of FSRS-5 (default parameters, adjustable desired retention 0.8–0.95).

#### [Lexpad](https://lexpad.app/features/smart-schedule)

  Lexpad is an AI vocabulary notebook for the words and phrases a learner meets, in any pair of 81 languages. The learner adds the words; AI writes each card (meanings, examples with translations, pronunciation, level). Words also come in from a browser extension (including clicking a word in YouTube subtitles), a Mac and Windows app, Kindle vocab.db and My Clippings, Anki `.apkg` and Quizlet exports, or ChatGPT and Claude through a remote MCP server.

- Five Leitner boxes are the default. The optional Smart schedule (Beta, chosen per notebook) is Lexpad's own implementation of FSRS-6 with the standard parameters, with desired retention 90% by default (80–97%).
- Personal tuning runs about once a month and is kept only if it predicts the learner's newest answers better.
- Two answer buttons, right or wrong. Smart schedule is free; Lexpad has a free plan and an optional Pro plan.

Available on the [web](https://app.lexpad.app), [Google Play](https://play.google.com/store/apps/details?id=app.lexpad.android), Mac and Windows ([Microsoft Store](https://apps.microsoft.com/detail/9NSFK2ZK6PFS)), and as an extension for Chrome, Edge and Firefox.

#### [LinGoat](https://lingoat.app/)

  LinGoat is an AI-powered language learning app that scores every word and grammar rule in every sentence you translate. Each item gets its own independent FSRS schedule, so reviews are driven by precise per-item recall data rather than sentence-level outcomes.

- Schedules word and grammar reviews using FSRS v6.
- Stacks multiple due or soon to be due review concepts into a single sentence to maximize useful reps per minute.
- Currently supports Spanish, with English and German coming soon. Free to get started. Supports learning Spanish from multiple languages.
- Available on web.

  LinGoat uses [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs) (FSRS-6) for scheduling.

#### [MemPro](https://mempro.me)

  MemPro is a web app for learning programming with spaced repetition. Besides concept cards, it has code exercises: you write C++, Python, Rust, TypeScript or Zig in the browser, and a sandbox runs tests against your solution. You then rate how well you remembered the card.

- Uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) for FSRS-6 scheduling with the default weights and 90% desired retention, at day granularity (short-term steps off).
- All topics are free to study. With a subscription, you can create your own topics, decks and cards in an editor or through an MCP server for Claude Code and Cursor.

#### [Ordkort](https://ordkort.com)

  Ordkort is a free, open-source ([AGPL-3.0](https://github.com/silicq/ordkort)) web app for learning vocabulary in 60 languages. It offers ready word lists for 29 topics at CEFR levels A1–C1, written by AI and checked against dictionaries (the official ordbokene.no for Norwegian, Wiktionary for other languages), plus a learner's dictionary, a grammar book and a translator that explains every word. No account, no ads, no tracking: cards live in the browser, devices sync end-to-end encrypted, and it works offline as a PWA.

- Its own JavaScript implementation of FSRS-4.5 with the default weights and 90% desired retention.
- Six study modes (flip, multiple choice, typing, listening, gap fill, mixed); a right word in the wrong form counts as Hard.

#### [RePoker](https://www.repokerpro.com/en)

  RePoker is a preflop trainer for No-Limit Texas Hold'em on iOS and Android. Players study complete 13x13 preflop range charts (opens, big-blind defense and 3-bet defense, including mixed strategies), then practice their own decisions in simulated hands. It is a study tool with no real-money play.

- Uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) v5 (FSRS-6 default weights, no per-user optimizer) with 90% desired retention, short-term steps and fuzz enabled, and a 365-day maximum interval.
- No rating buttons. In Learn (preflop range study), a correct answer within the time limit (7 seconds by default, adjustable per deck) is `Easy` unless the previous review was `Again` or `Hard`; any other correct answer is `Good`, and a wrong answer is `Again`. `Hard` is never produced.
- In Practice (simulated hands), grading has two levels and ignores time: getting the whole action line right is `Good`, anything else is `Again`.
- Progress is stored on device and core training works offline.
- Commercial app: free to download with a guided introduction; full training requires a subscription.

Available on [App Store](https://apps.apple.com/app/id6749474456) and [Google Play](https://play.google.com/store/apps/details?id=fun.codechat.poker.repoker).

#### [Rhythm Word](https://rhythmword.com)

  Rhythm Word is an iOS vocabulary learning app that helps users build and retain English vocabulary through AI-generated context sentences and spaced repetition.

  Rhythm Word implements FSRS-4.5 for intelligent review scheduling.

#### [Smort](https://getsmort.com)

  Smort is an iPhone app for language learners who understand more than they can say. You talk out loud with Smort, an AI conversation partner, keep the words you want from each chat as flashcards, and answer them out loud from memory. It also imports Anki `.apkg` decks, with the study progress it supports.

- Uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) (FSRS-6) on the device, through JavaScriptCore, at 90% desired retention by default.
- Each answer gets a grade, from Smort's answer check or from the learner, and the grade becomes the FSRS rating.
- Paid app (Smort Plus), with a 7-day free trial. iPhone, iOS 26.4 or later.

Available on [App Store](https://apps.apple.com/app/id6789021306).

#### [Verbamor](https://verbamor.com)

  Verbamor is an iOS app for people who take language lessons or have real conversations in a new language. It records the lesson, transcribes it, and turns the words and phrases you met into flashcards, each with a picture, an example sentence and audio. It covers Spanish, French, Italian, Portuguese and Russian.

- Uses [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs) (FSRS-6) at 90% desired retention to schedule every card.
- A nightly job refits each learner's FSRS-6 parameters from their own review history once they have enough reviews, and keeps the new parameters only when they fit better.
- Cards come from your own lessons, plus a starter deck of about 650 common words in each language.
- Paid app, with a 7-day free trial on the annual plan. iPhone, iPad and Apple Watch.

Available on [App Store](https://apps.apple.com/app/id6789744088).

#### [Word2Sentence](https://github.com/ArabidopsisDev/Word2Sentence)

Word2Sentence is a local-first Windows desktop app for learning vocabulary through sentence production. AI generates multilingual writing scenarios, provides inline feedback and post-answer usage cards, and automatically evaluates target-word recall without self-rating buttons.

- Uses a deterministic C# FSRS-6 scheduler validated against `py-fsrs 6.3.1`, with 90% desired retention.
- Supports English and Simplified Chinese UI, configurable target and explanation languages, and local JSON storage.

#### [WordVault](https://aerolith.org/wordvault/)

  WordVault is a word study app for Scrabble/Boggle/other word games. It [uses the Go FSRS library](https://github.com/open-spaced-repetition/go-fsrs) for scheduling words, which show up as scrambled letters for the user to solve. This should hopefully be significally more efficient than the Leitner cardbox system previously in use in some word study apps.

  See [announcement blog post](https://cesardelsolar.com/posts/2024-10-13-wordvault/).

## Related

### Algorithm

#### FSRS

- Math:
  - [The Algorithm · open-spaced-repetition/awesome-fsrs Wiki](https://github.com/open-spaced-repetition/awesome-fsrs/wiki/The-Algorithm)
- Dataset:
  - [open-spaced-repetition/anki-revlogs-10k · Datasets at Hugging Face](https://huggingface.co/datasets/open-spaced-repetition/anki-revlogs-10k) (latest)
  - [open-spaced-repetition/FSRS-Anki-20k · Datasets at Hugging Face](https://huggingface.co/datasets/open-spaced-repetition/FSRS-Anki-20k) (deprecated)
- Benchmark: [open-spaced-repetition/srs-benchmark: A benchmark for spaced repetition schedulers/algorithms (github.com)](https://github.com/open-spaced-repetition/srs-benchmark)
- FSRS Explained with Code: [Implementing FSRS in 100 Lines](https://borretti.me/article/implementing-fsrs-in-100-lines)

#### MaiMemo

- Code:
  - [maimemo/SSP-MMC: A Stochastic Shortest Path Algorithm for Optimizing Spaced Repetition Scheduling](https://github.com/maimemo/SSP-MMC)
  - [maimemo/SSP-MMC-Plus: Optimizing Spaced Repetition Schedule by Capturing the Dynamics of Memory](https://github.com/maimemo/SSP-MMC-Plus)
- Paper: 
  - [A Stochastic Shortest Path Algorithm for Optimizing Spaced Repetition Scheduling - Proceedings of the 28th ACM SIGKDD Conference on Knowledge Discovery and Data Mining](https://dl.acm.org/doi/10.1145/3534678.3539081?cid=99660547150) [[中文版](https://memodocs.maimemo.com/docs/2022_KDD)]
  - [Optimizing Spaced Repetition Schedule by Capturing the Dynamics of Memory - IEEE Journals & Magazine - IEEE Xplore](https://ieeexplore.ieee.org/document/10059206) [[中文版](https://memodocs.maimemo.com/docs/2023_TKDE)]
- Dataset: [MaiMemo's Open-Source Memory Behavior Dataset for Spaced Repetition](https://doi.org/10.7910/DVN/VAGUL0) [[中文介绍](https://memodocs.maimemo.com/docs/dataset)]
- Science popularization video:
  - [【墨墨科普】为了搞懂艾宾浩斯记忆法的虚假与真相，我回到了 1885 年……_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1yF411s7SN/)
  - [【墨墨科普】降维打击！别用艾宾浩斯记忆法了，试试这个吧！_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1mL4y1P7bh/)
  - [【墨墨科普】几个公式，拯救你的记忆。_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Xe4y1t7Mi/)
- Wiki: [墨墨百科](https://memodocs.maimemo.com/docs/algorithm-intro)

#### HLR

  An algorithm made particularly for second language acquisition. The HLR model marries psycholinguistic theory with modern machine learning techniques, estimating the "half-life" of words (and potentially any other item or fact) in a student's long-term memory.

- GitHub repository: [duolingo/halflife-regression](https://github.com/duolingo/halflife-regression)
- Paper: [A Trainable Spaced Repetition Model for Language Learning](https://github.com/duolingo/halflife-regression/blob/master/settles.acl16.pdf)

#### DASH

- Paper: [Probabilistic Models of Student Learning and Forgetting Public Deposited](https://scholar.colorado.edu/concern/graduate_thesis_or_dissertations/zp38wc97m)
- Paper: [Memory Models for Spaced Repetition Systems](https://www.politesi.polimi.it/retrieve/b39227dd-0963-40f2-a44b-624f205cb224/2022_4_Randazzo_01.pdf)

#### ACT-R

- Paper: [An ACT-R Model of the Spacing Effect](http://act-r.psy.cmu.edu/wordpress/wp-content/themes/ACT-R/workshops/2003/proceedings/46.pdf)

#### SuperMemo

  SuperMemo was the first software that used computer-based spaced repetition algorithms and pioneered the usage of machine learning to personalize each user's learning schedule.

- SM-0: [The birthday of spaced repetition: July 31, 1985](https://supermemo.guru/wiki/The_birthday_of_spaced_repetition:_July_31,_1985)
- SM-2: [Application of a computer to improve the results obtained in working with SuperMemo method](https://super-memory.com/english/ol/sm2.htm)
- SM-5: [First fast-converging spaced repetition algorithm: Algorithm SM-5](https://supermemo.guru/wiki/First_fast-converging_spaced_repetition_algorithm:_Algorithm_SM-5)
- SM-17: [Algorithm SM-17](https://supermemo.guru/wiki/Algorithm_SM-17)

#### Leitner System

  Leitner sytem sorts flashcard into groups according to how well the learner knows each one in Leitner's learning box. The learners try to recall the answer written on a flashcard. If they succeed, the card is sent to the next box. If they fail, the card is sent back to the first box. In each successive box, the amount of time before the learner is required to revisit the cards increases. (More: [Wikipedia](https://en.wikipedia.org/wiki/Leitner_system))

