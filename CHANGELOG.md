# Changelog

## Unreleased
### Fixed
- **Context Compression**: Fixed JSON decode error handling when auxiliary LLM returns non-JSON responses (e.g., HTML, plain text, malformed JSON). Added explicit `json.JSONDecodeError` handling in `agent/context_compressor.py` with:
  - Detailed error logging including provider, model, base URL, and JSON error position
  - Immediate fallback to main model if separate summary model is configured
  - Shorter 30-second cooldown when JSON decode fails on main model
  - Preserved existing fallback logic for model not found, timeouts, and transient errors
- Resolves warning: `Failed to generate context summary: Expecting value: line X column Y (char Z)`
