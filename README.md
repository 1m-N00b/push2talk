![a push to talk logo created by dall-e](./pictures/logo-small.png)

# Push to talk - working with both wayland/x11 and pulseaudio (pipewire)

## 🥅How to use it ?

At start it will mute all your sources (microphone) and then you will have to press <kbd>Control_Left</kbd>+<kbd>Space</kbd> to unmute.
You can release <kbd>Space</kbd><kbd>Control_Left</kbd> then to mute again.

- You can pause/resume the program with sending a `SIGUSR1` signal.

## ⚠️ Requirements

User have to be in `input` group (or maybe `plugdev`, depend your distro, check file under `/dev/input/*`).

```bash
sudo usermod -a -G plugdev $USER
sudo usermod -a -G input $USER
```

## 📦 Installation

- There is a AUR for [archlinux](https://aur.archlinux.org/packages/push2talk-git)
- For other distro, you can `cargo install --git https://github.com/cyrinux/push2talk`

## 🎤 Usage

- To set keybind compose of one or two keys, use env var, eg: `env PUSH2TALK_KEYBIND="ControlLeft,KeyO" push2talk` or `env PUSH2TALK_KEYBIND="MetaRight" push2talk`.

- To get more log: `push2talk [-vvv]`.
- To specify an unique source to manage use the `--source device`.
- There is also a systemd unit provided. `systemctl --user start push2talk.service`
