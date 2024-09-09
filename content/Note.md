---
id: Note
aliases: []
tags: []
---

- For onboarding requests, we also should need hotelId to make it dynamic

app_id: fb824982-14d5-4c30-aa34-459812ee3d9d (Prod)
app_id: baeab50f-9baa-4d4e-a68b-70b067b4ea74 (Dev)

ggopatYJP1ZE2FZLvastdumb-u



## Command to add shortcuts in dconf(Gnome)

```bash
dconf write /org/gnome/desktop/wm/keybindings/switch-to-workspace-5 "['<Super>5']"
dconf write /org/gnome/desktop/wm/keybindings/switch-to-workspace-6 "['<Super>6']"
```

(source)[https://www.reddit.com/r/pop_os/comments/vcgtjn/how_to_add_shortcut_to_switch_to_workspace_5_6/]

## Tmux Configuration if it went missing

```zsh
set -g mouse on
setw -g mode-keys vi
set -g default-terminal "screen-256color"
set -g default-terminal "alacritty" 
set-option -sa terminal-overrides ",alacritty*:Tc" 
set -as terminal-features ",alacritty:usstyle"

set -g pane-border-style fg=colour236
set -g pane-active-border fg=colour236


bind b switch-client -t default-session
bind p send-keys -t default-session C-p C-m \; switch-client -t default-session;
# bind z new-session -s tasks 'nvim /home/satrujit/dev/personal/notes/tasks.md' \; switch-client -t tasks
bind z if-shell "[ -z \"\$(tmux list-sessions | grep -w tasks)\" ]" "new-session -s tasks 'nvim /home/satrujit/dev/personal/notes/tasks.md'" "switch-client -t tasks"


bind -T copy-mode-vi v send -X begin-selection
bind -T copy-mode-vi y send-keys -X copy-pipe-and-cancel "pbcopy"
bind P paste-buffer
bind -T copy-mode-vi MouseDragEnd1Pane send-keys -X copy-pipe-and-cancel "pbcopy"
```

- the search api shouldn't send the list of the employees if it is gm or person is not verified it's image


https://gitlab.gnome.org/GNOME/gnome-software/-/issues/2558


## Data I will send in urlparamter
- HotelId (Optional)
- DepartmentType
- LocationData
- ticketId
- redirectUrl
- (One Time task)

- Whatever data will I send shouldn't be able to change
- Task create
- Order convert
