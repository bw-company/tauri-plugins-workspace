---
"shell": patch:bug
"shell-js": patch:bug
---

Apply the default open validation regex `^((mailto:\w+)|(tel:\w+)|(https?://\w+)).+` when the open configuration is not set, preventing unchecked input from being used in this scenario (previously the plugin would skip validation when it should disable all calls). This keeps backwards compatibility while still fixing this vulnerability.
The scope is no longer validated for Rust calls via `ShellExt::shell()` so if you need to block JavaScript from calling the API you can simply set `tauri.conf.json > plugins > shell > open` to `false`.
