# Deutsch Studieren

[![Live site](https://img.shields.io/badge/live%20site-GitHub%20Pages-2ea44f?logo=github)](https://unknown-x0.github.io/Deutsch-Studieren/)
[![Version](https://img.shields.io/github/v/tag/UNKNOWN-X0/Deutsch-Studieren?label=version)](https://github.com/UNKNOWN-X0/Deutsch-Studieren/tags)
[![JavaScript](https://img.shields.io/badge/JavaScript-vanilla-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

A browser-based German vocabulary trainer with typed answers, multiple choice, matching pairs, and performance-weighted word practice.

**[Open Deutsch Studieren →](https://unknown-x0.github.io/Deutsch-Studieren/)**

## Features

- **Two directions:** practice German-to-English or English-to-German.
- **Three modes:** typed answers, multiple choice, or matching pairs.
- **Two vocabulary sources:** the bundled word list, or topic-based words fetched online.
- **Progress tracking:** correct answers, practice streaks, and progress per word.
- **Spaced repetition:** words you miss come back more often.
- **Example sentences:** shown when the bundled vocabulary has one.

## Getting started

### Use it online

Open the [live app](https://unknown-x0.github.io/Deutsch-Studieren/), choose a vocabulary source, category or topic, direction, and practice mode, then select **Start Practice**.

### Run it yourself

Download or clone the repository and open `index.html` in a modern browser. No build step or package installation is required.

```sh
git clone https://github.com/UNKNOWN-X0/Deutsch-Studieren.git
open Deutsch-Studieren/index.html
```

The bundled vocabulary works without network access; online topic vocabulary needs an internet connection.

## Usage

### Online vocabulary

Topic-based vocabulary uses [Datamuse](https://www.datamuse.com/api/) to find related English words and [MyMemory](https://mymemory.translated.net/) to translate them into German. Online results depend on those services and your network connection. The bundled vocabulary is available as a separate source.

## Privacy

Practice progress is stored in your browser's local storage under `germanSRS`; clearing browser storage removes it. Online mode sends the requested topic to Datamuse and the vocabulary terms to MyMemory. Nothing else leaves the browser.

## Tests

```sh
node --test tests/*.test.cjs
```

The tests load the scripts against a fake page and check the practice modes, scoring, and progress storage.

## Project structure

```text
index.html, styles.css                      Page structure and visual styling
words.js                                    Bundled German vocabulary and examples
js/state.js, js/dom.js                      Shared state and DOM references
js/setup.js                                 Initialization and event wiring
js/practice.js, js/answers-and-progress.js  Practice flow, scoring, and progress
js/multiple-choice.js, js/matching.js       Practice mode behavior
js/spaced-repetition.js                     Word weights and local progress storage
js/vocabulary-api.js                        Topic search and translation requests
tests/                                      Functionality regression tests
```

The app uses classic browser scripts. Keep the script order in `index.html` when changing module files.

## License

MIT. See [LICENSE](LICENSE).
