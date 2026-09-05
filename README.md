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

#### [Discito](https://discito.app)

  Discito is a native iOS flashcard app built around FSRS-6, with iCloud sync, on-device AI card generation, lecture-audio-to-flashcards, image occlusion authoring, and full-fidelity `.apkg` import/export. One-time purchase, no subscription.

  Discito uses its own Swift FSRS-6 port (validated for parity against [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs)), with the parameter optimizer bridging [fsrs-rs](https://github.com/open-spaced-repetition/fsrs-rs) via swift-bridge FFI.

#### [Flipnem](https://flipnem.com/)

An Anki compatible online Flashcard platform that supports PWA install.

- Mnemonics, Deck Encryption, Deck Sharing, and an optional public profile to show off your progress
- An MCP server that allows user to connect their own AI agent to their collections for quizzing, deck management, and mnemonic reinforcement.
- Free and paid tiers
- FSRS scheduled flashcard reviews that rely on [rs-fsrs](https://github.com/open-spaced-repetition/rs-fsrs)

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

### Note-taking

#### [Logseq](https://logseq.com/)

  A privacy-first, open-source platform for knowledge management and collaboration. It focuses on privacy, longevity, and user control.

  Logseq uses [cljc-fsrs](https://github.com/open-spaced-repetition/cljc-fsrs) in its database version.

#### [Obsidian](https://obsidian.md/)

  A personal notes, journaling, knowledge base, and project management application that allows the user to easily visualize relationships between information in graph form. Connect your notes via hyperlinks and install many community plugins made for Obsidian.

  - [obsidian-spaced-repetition-recall](https://github.com/open-spaced-repetition/obsidian-spaced-repetition-recall) is a modified version of obsidian-spaced-repetition and merging recall plugin to use seperate json data file. It uses FSRS-6.

  - [HiNote](https://github.com/CatMuse/HiNote) is a powerful Obsidian extension that helps you add comments to highlighted notes, use AI for thinking, and FSRS-6 for memory.

  - [LearnKit](https://github.com/ctrlaltwill/LearnKit) helps you remember what you write. It brings flashcards, note review, tests, and AI-assisted study tools into Obsidian, so your vault becomes a place to learn, not just store information. It uses FSRS-6 for spaced repetition scheduling.

  - [True Recall](https://github.com/pieralukasz/true-recall) is a next-gen spaced repetition system for Obsidian with AI card generation, local-first SQLite storage, Anki import/export, projects system, and comprehensive analytics. It uses FSRS-6 via [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs).

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

#### [Chessbook](https://chessbook.com/)

  Mobile and web chess study application that combines multiple resources from YouTube, Lichess, ChessBase, and books to create a custom personal chess repertoire.

  Chessbook overhauled its spaced repetition system [using FSRS-4.5](https://x.com/chessbookcom/status/1805137108991946775).

#### [HSRS](https://github.com/satchelspencer/hsrs) 

Intended for language learning, HSRS continuously refreshes card content using a system of parameterized grammar cards. Individual reviews of a card reschedule all sub-cards in the parameter tree using bayesian statistics to estimate the contributions of each. Changes to stability from FSRS are interpolated in retrievability-space according to their probability. 

Used to power [grsly](https://grsly.com/), a tool for learning Japanese grammar.

#### [KaChiKa](https://kachika.app/)

  KaChiKa is an AI-powered photo-to-flashcard app for language learners. Snap a photo of any object — a coffee cup, a cat, a street sign — and KaChiKa extracts the vocabulary, generates real-world example sentences, and schedules reviews using FSRS.

  Supports English, Japanese, French, Korean, Italian, Spanish, and Chinese. All photos are stored locally on device for privacy. Available on iOS, Android, and APK.

#### [LeetFlash](https://leetflash.com/)

  LeetFlash is a flashcard review app for review LeetCode algorithm questions. It leverages TS-FSRS for scheduling flashcards.

  The app consists of a Chrome extension, website for now. A mobile app is under development. It can automatically capture LeetCode question submissions and schedule your next review using an Anki-like experience. It supports both Leetcode and Leetcode China (力扣).

#### [LinGoat](https://lingoat.app/)

  LinGoat is an AI-powered language learning app that scores every word and grammar rule in every sentence you translate. Each item gets its own independent FSRS schedule, so reviews are driven by precise per-item recall data rather than sentence-level outcomes.

- Schedules word and grammar reviews using FSRS v6.
- Stacks multiple due or soon to be due review concepts into a single sentence to maximize useful reps per minute.
- Currently supports Spanish, with English and German coming soon. Free to get started. Supports learning Spanish from multiple languages.
- Available on web.

  LinGoat uses [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs) (FSRS-6) for scheduling.

#### [Rhythm Word](https://rhythmword.com)

  Rhythm Word is an iOS vocabulary learning app that helps users build and retain English vocabulary through AI-generated context sentences and spaced repetition.

  Rhythm Word implements FSRS-4.5 for intelligent review scheduling.

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
