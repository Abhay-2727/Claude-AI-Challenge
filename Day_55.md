Today's cahnges:

[API.md](https://github.com/user-attachments/files/30368691/API.md)

✅ Day 5 Summary

What was built:

Switched AI provider from Anthropic Claude to Google Gemini (free tier, no billing) — flagged and explained before implementing, since it deviated from the original PRD
generate_outline() — real, working Gemini call producing structured Markdown outlines
generate_draft() — real, working Gemini call expanding outlines into full coherent drafts
Wired both into app.py with proper session state management (draft clears when a new outline is generated, preventing stale mismatches)
MOCK_MODE retained as a fallback safety net for both functions

Debugged along the way:

A formatting artifact (stray tag) that broke the first ai.py paste
Two rounds of Gemini model deprecation (gemini-2.0-flash → gemini-2.5-flash → gemini-flash-latest), landing on the version-proof alias so this shouldn't recur
Confirmed real end-to-end output with your own resume content — both outline and draft correctly captured names, IDs, and project details

Verified working:

✅ Full flow: input → outline → draft, tested with real content
✅ No cost, no billing risk — free tier only
✅ docs/API.md updated to reflect the provider change
✅ Committed and pushed to GitHub
🎯 Tomorrow (Day 6): Persistent Storage — Save, Search & Tags

We'll build app/storage.py with SQLite: auto-saving every completed session, plus a sidebar history panel with search and tag filtering. This is the "organizing" half of Inkstruct's value — turning today's one-off generations into a searchable library of past work.

No setup needed — today's extracted_text, outline, and draft variables in st.session_state are exactly what tomorrow's save function will persist.
