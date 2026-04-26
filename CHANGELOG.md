## [1.6.1] — 2026-04-27

### Fixed
- **Ctrl+C copy/interrupt conflict in CLI** — Separated copy from interrupt:
  - Added `display.copy_shortcut` config option (`auto` | `ctrl_c` | `ctrl_shift_c` | `disabled`)
  - Ctrl+Shift+C now defers to terminal emulator for native copy (Linux/Windows standard)
  - Ctrl+Q added as alternative interrupt/exit shortcut
  - TUI already had correct selection-aware Ctrl+C behavior; no code change needed

### Changed
- `hermes_cli/config.py`: added `copy_shortcut` default with platform-aware `auto` setting
- `cli.py`: added `handle_ctrl_shift_c` (no-op) and `handle_ctrl_q` (interrupt) keybindings

### Documentation
- Updated TUI hotkeys help to reflect platform-aware copy behavior
