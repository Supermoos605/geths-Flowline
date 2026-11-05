# Flowline Canva leaderboard and chat update

This update applies to the Canva-exported standalone HTML file, not the repository's separate root `index.html`.

## Fixes

- Rebuilt the live leaderboard rows with DOM nodes and `textContent`, rather than malformed template placeholders. This restores player names, rank dots, and distances without interpreting names as HTML.
- Rebuilt the deepest-lines list the same way; the previous renderer displayed a literal `{esc(e.n)}` instead of the player's name.
- Normalizes display names with Unicode NFKC and strips control characters while preserving ordinary international letters.
- Collapsed Rider Radio into a `RIDER CHAT` launcher. Clicking it opens/closes the chat panel.
- Counts newly arriving messages while the chat is closed and shows the unread count on the launcher. Opening chat clears the count; messages received while the panel is open do not add unread notifications.
- Keeps the most recent 30 chat messages visible and preserves the existing Canva Sheet data flow.

## Apply

Use the accompanying `Flowline-Canva-Live-Leaderboard-v2.html` generated in this ChatGPT conversation as the updated Canva HTML. The original root GitHub Pages `index.html` remains untouched because it uses a different multiplayer implementation.

The final inline JavaScript was checked with `node --check` after the changes.
