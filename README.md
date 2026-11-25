# Answerly FAQ chatbot

A lightweight, browser-only FAQ chatbot. It preprocesses questions by lowercasing, removing punctuation, removing common English stop words, and tokenizing. It then builds TF-IDF vectors for the stored FAQ questions and uses cosine similarity to choose an answer. If the best match is below the adjustable threshold, the assistant asks the visitor to rephrase or contact support.

## Run it

No build step, account, or package installation is needed. Open `index.html` in a modern browser. To serve it locally instead, run `python -m http.server 8000` from this folder and visit `http://localhost:8000`.

## Edit the FAQ collection

The starter questions and answers are in `faqs.json` and are also embedded in `app.js` so the app works directly from a `file://` URL. For a quick topic change, update `SAMPLE_FAQS` in `app.js` and the matching entries in `faqs.json`. Visitors can also add, edit, or delete FAQs through **Manage FAQs**. Those changes and the similarity threshold are saved in the current browser using `localStorage`; choose **Restore sample FAQs** to undo local edits.

The match threshold ranges from 0.03 to 0.65. A lower value accepts looser matches; a higher value requires a closer match. The default is 0.12.

## Files

- `index.html` — chat interface and FAQ manager
- `styles.css` — responsive visual styling
- `app.js` — preprocessing, TF-IDF / cosine matching, chat behavior, and FAQ editing
- `faqs.json` — editable sample FAQ data
