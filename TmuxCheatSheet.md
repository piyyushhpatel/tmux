# tmux Cheat Sheet

A quick reference guide for **tmux** (terminal multiplexer) concepts, key bindings, and command-line usage.

> **Note on Prefix Key:**  
> By default, all key bindings in tmux are preceded by the prefix key: `Ctrl + b` (written as `C-b`).

---

## 🚀 Basic Concepts & Workflow

* **Server:** The background process managing all sessions.
* **Session:** A collection of windows under a specific name.
* **Window:** A single screen within a session (like tabs in a browser).
* **Pane:** A subdivided section of a window (splits).

---

## 📦 Session Management

### From the Terminal Shell

| Command | Description |
| :--- | :--- |
| `tmux` | Start a new unnamed session |
| `tmux new -s <session_name>` | Start a new named session |
| `tmux ls` (or `tmux list-sessions`) | List all running sessions |
| `tmux attach -t <session_name>` | Attach to a specific session |
| `tmux attach` (or `tmux a`) | Attach to the last used session |
| `tmux kill-session -t <session_name>` | Kill a specific session |
| `tmux kill-server` | Kill all sessions and stop the tmux server |

### Key Bindings (Inside tmux)

| Key Binding | Action |
| :--- | :--- |
| `C-b d` | Detach from the current session |
| `C-b ($)` | Rename the current session |
| `C-b s` | Interactive session chooser (switch between sessions) |

---

## 🪟 Window Management

| Key Binding | Action |
| :--- | :--- |
| `C-b c` | Create a new window |
| `C-b ,` | Rename current window |
| `C-b w` | Interactive list of windows and sessions |
| `C-b n` | Move to the **next** window |
| `C-b p` | Move to the **previous** window |
| `C-b <number>` | Switch directly to window by number (0-9) |
| `C-b &` | Kill the current window |

---

## 🔲 Pane Management (Splits)

### Creating Panes

| Key Binding | Action |
| :--- | :--- |
| `C-b %` | Split current pane **vertically** (side-by-side) |
| `C-b "` | Split current pane **horizontally** (top-bottom) |

### Navigating Panes

| Key Binding | Action |
| :--- | :--- |
| `C-b <Arrow Key>` | Move focus to the pane in that direction |
| `C-b o` | Cycle focus to the next pane |
| `C-b q` | Display pane numbers (press number to jump to pane) |

### Resizing & Arranging Panes

| Key Binding | Action |
| :--- | :--- |
| `C-b C-<Arrow Key>` | Resize pane by 1 cell in direction |
| `C-b Alt-<Arrow Key>` | Resize pane in larger steps |
| `C-b z` | Toggle **fullscreen/zoom** for current pane |
| `C-b Space` | Cycle through preset pane layouts |
| `C-b {` | Move current pane left/up |
| `C-b }` | Move current pane right/down |
| `C-b x` | Close/kill current pane |

---

## 📜 Copy Mode & Scrolling

| Key Binding | Action |
| :--- | :--- |
| `C-b [` | Enter Copy Mode (allows scrolling) |
| `q` | Exit Copy Mode |
| `PageUp` / `PageDown` | Scroll through history in Copy Mode |
| `Space` | Start selection (in default copy mode) |
| `Enter` | Copy selected text and exit Copy Mode |
| `C-b ]` | Paste copied text buffer |

---

## ⚙️ Command Mode & Misc

| Key Binding | Action |
| :--- | :--- |
| `C-b :` | Open tmux command prompt |
| `C-b ?` | Display list of all active key bindings |
| `C-b t` | Display a big digital clock in current pane |

### Useful Commands (Entered via `C-b :`)

```text
:source-file ~/.tmux.conf    # Reload tmux configuration file
:set -g mouse on              # Enable mouse support (clicking, resizing, scrolling)
:set -g status-bg blue        # Change status bar background color
```

---

## 💡 Quick Tips for `~/.tmux.conf`

Create or edit `~/.tmux.conf` to customize your setup:

```tmux
# Enable mouse support
set -g mouse on

# Remap prefix from 'C-b' to 'C-a'
unbind C-b
set-option -g prefix C-a
bind-key C-a send-prefix

# Start window and pane indexing at 1 instead of 0
set -g base-index 1
setw -g pane-base-index 1

# Easy configuration reload
bind r source-file ~/.tmux.conf \; display "Config Reloaded!"
```
