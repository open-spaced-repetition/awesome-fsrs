[<img src="https://github.com/open-spaced-repetition/fsrs4anki/assets/32575846/9efb2ca5-51bd-411d-9694-a77b09f51fa7" align="left" width="64" height="64">](https://github.com/open-spaced-repetition/awesome-fsrs)

# Awesome FSRS [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A curated list of awesome FSRS implementations, papers and resources. Feel free to suggest new projects in Issues or PR directly.

## Implementation

- Python
  - Scheduler (v5): [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs)
  - Optimizer: [fsrs-optimizer](https://github.com/open-spaced-repetition/fsrs-optimizer)
  - [Deprecated] Optimizer: [fsrs-optimizer-tiny](https://github.com/open-spaced-repetition/fsrs-optimizer-tiny)
- Rust
  - Scheduler (v5) + Optimizer: [fsrs-rs](https://github.com/open-spaced-repetition/fsrs-rs)
    - Run in browsers: [fsrs-browser](https://github.com/open-spaced-repetition/fsrs-browser)
- TypeScript
  - Scheduler (v5): [ts-fsrs](https://github.com/open-spaced-repetition/ts-fsrs)
- Go
  - Scheduler (v5): [go-fsrs](https://github.com/open-spaced-repetition/go-fsrs)
- Dart
  - Scheduler (v4.5): [dart-fsrs](https://github.com/open-spaced-repetition/dart-fsrs)
- Swift
  - Scheduler (v4.5): [swift-fsrs](https://github.com/open-spaced-repetition/swift-fsrs)
- Clojure/ClojureScript
  - Scheduler (v4): [cljc-fsrs](https://github.com/open-spaced-repetition/cljc-fsrs)
- Ruby
  - Scheduler (v4): [rb-fsrs](https://github.com/open-spaced-repetition/rb-fsrs)
- Kotlin
  - Scheduler (v4): [android-fsrs](https://github.com/open-spaced-repetition/android-fsrs)
- Elixir
  - Scheduler (v4): [ex_fsrs](https://github.com/open-spaced-repetition/ex_fsrs)

## Application

### Flashcard

- #### Anki (https://apps.ankiweb.net/)

  Free and open source, content-agnostic flashcard application for Windows, Mac, Linux, iPhone, and Android. Supports text, images, audio, videos, and scientific markup (via LaTex). Offers free synchronization service using AnkiWeb, with community-shared add-ons and decks.

  - FSRS available as an opt-in feature replacing the default SM-2 algorithm.
  - Additionally, this [add-on](https://ankiweb.net/shared/info/759844606) offers a variety of extra features, such as Postpone, Advance, Load Balancing and Easy Days.

### Note-taking

- #### RemNote (https://www.remnote.com/)

  Multiplatform note-taking application with a simple and streamlined process of creating flashcards. Has an active community with student-made materials for exam preparation. Available for offline and online usage.

  RemNote integrated FSRS-4.5 into its scheduling system in [release 1.16](https://feedback.remnote.com/changelog/remnote-1-16-ultimate-spaced-repetition).

- #### Obsidian (https://obsidian.md/)

  A personal notes, journaling, knowledge base, and project management application that allows the user to easily visualize relationships between information in graph form. Connect your notes via hyperlinks and install many community plugins made for Obsidian.

  FSRS is available as an extension for Obsidian: [obsidian-spaced-repetition-recall](https://github.com/open-spaced-repetition/obsidian-spaced-repetition-recall).

### Others

- #### Chessbook (https://chessbook.com/)

  Mobile and web chess study application that combines multiple resources from YouTube, Lichess, ChessBase, and books to create a custom personal chess repertoire.

  Chessbook overhauled its spaced repetition system [using FSRS-4.5](https://x.com/chessbookcom/status/1805137108991946775).

## Related

### Algorithm

- #### FSRS

  - Paper: [A Stochastic Shortest Path Algorithm for Optimizing Spaced Repetition Scheduling | Proceedings of the 28th ACM SIGKDD Conference on Knowledge Discovery and Data Mining](https://dl.acm.org/doi/10.1145/3534678.3539081?cid=99660547150)
  - Paper: [Optimizing Spaced Repetition Schedule by Capturing the Dynamics of Memory | IEEE Journals & Magazine | IEEE Xplore](https://ieeexplore.ieee.org/document/10059206)
  - Dataset: [open-spaced-repetition/FSRS-Anki-20k · Datasets at Hugging Face](https://huggingface.co/datasets/open-spaced-repetition/FSRS-Anki-20k)
  - Benchmark: [open-spaced-repetition/srs-benchmark: A benchmark for spaced repetition schedulers/algorithms (github.com)](https://github.com/open-spaced-repetition/srs-benchmark)

- #### Leitner System

  Leitner sytem sorts flashcard into groups according to how well the learner knows each one in Leitner's learning box. The learners try to recall the answer written on a flashcard. If they succeed, the card is sent to the next box. If they fail, the card is sent back to the first box. In each successive box, the amount of time before the learner is required to revisit the cards increases. (More: [Wikipedia](https://en.wikipedia.org/wiki/Leitner_system))

- #### SuperMemo algorithms

  SuperMemo was the first software that used computer-based spaced repetition algorithms and pioneered the usage of machine learning to personalize each user's learning schedule.

  - SM-0: [The birthday of spaced repetition: July 31, 1985](https://supermemo.guru/wiki/The_birthday_of_spaced_repetition:_July_31,_1985)
  - SM-2: [Application of a computer to improve the results obtained in working with SuperMemo method](https://super-memory.com/english/ol/sm2.htm)
  - SM-5: [First fast-converging spaced repetition algorithm: Algorithm SM-5](https://supermemo.guru/wiki/First_fast-converging_spaced_repetition_algorithm:_Algorithm_SM-5)
  - SM-17: [Algorithm SM-17](https://supermemo.guru/wiki/Algorithm_SM-17)

- #### ACT-R

  - Paper: [An ACT-R Model of the Spacing Effect](http://act-r.psy.cmu.edu/wordpress/wp-content/themes/ACT-R/workshops/2003/proceedings/46.pdf)

- #### DASH

  - Paper: [Probabilistic Models of Student Learning and Forgetting Public Deposited](https://scholar.colorado.edu/concern/graduate_thesis_or_dissertations/zp38wc97m)
  - Paper: [Memory Models for Spaced Repetition Systems](https://www.politesi.polimi.it/retrieve/b39227dd-0963-40f2-a44b-624f205cb224/2022_4_Randazzo_01.pdf)

- #### Duolingo's Half-Life Regression algorithm

  An algorithm made particularly for second language acquisition. The HLR model marries psycholinguistic theory with modern machine learning techniques, estimating the "half-life" of words (and potentially any other item or fact) in a student's long-term memory.

  - GitHub repository: [duolingo/halflife-regression](https://github.com/duolingo/halflife-regression)
  - Paper: [A Trainable Spaced Repetition Model for Language Learning](https://github.com/duolingo/halflife-regression/blob/master/settles.acl16.pdf)
