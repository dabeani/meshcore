# Changelog

All notable changes to this project.

## [v0.9.8] (unreleased)

### Added
- Mgmt / Contacts; added "Purge w/o favs" (purge all contacts except favourites).

### Changed / Improved
- Mgmt / UI Zoom can now be changed with "^" or "v" buttons.
- Mgmt / Contacts; Auto Add Types can now be set with freely combinable toggles (USR/RPT/SRV/SNS/OW) when Auto Add is disabled.
- Mgmt / Contacts; Auto Add Types now shows clearer labels (e.g., "USR (Users)").
- Contacts / Repeater Admin; reorganized Login screen layout to prevent status text overlap and improve readability.
- Contacts / Repeater Admin; added live login status lines (Direct/Flood send mode, wait countdown, result, role).
- Mgmt / UI -> UI Zoom; improved zoom step granularity for finer control with extra buttons for more/less zoom.

### Fixed
- Mgmt / Channels; fixed an issue where adding a new #hashtag channel could show "Channel exists" and could lead to duplicate message display.
- Mgmt / UI; fixed Tiles Folder picker showing empty after reboot until Map was opened once.
- MAP; fixed an issue while moving the map out of touch and after returning, where the map would jump back to the original position.
- Contacts / Repeater Admin; fixed Login button hit-test offset in Contact Detail overlay.
- Contacts / Repeater Admin; fixed repeater password NVS persistence detection (saved state) and empty-password save/load handling.

---

## [v0.9.7]

### Added
- Sync settings to SDCard and load from SDCard on boot (if present) for easy backup/restore of settings.
- MAP; GPS Accuracy Circle Implementation - when GPS accuracy is available, a light blue circle is drawn around the GPS position indicating the accuracy radius (HDOP-based accuracy estimation (HDOP × 2.0 meters)).

### Changed / Improved
- Contacts / Repeater Admin Menu; Modified the contact selection logic to only reset the repeater admin state when actually switching to a different repeater.
- MAP; improved GPS accuracy circle rendering (smoother edges).
- Contacts / Repeater Admin Menu; improved to be allowed to login with empty password.
- Discovered (Contacts) - Discovered Contacts list is now only sorted by "last heard" (newest on top) to make it easier to find recently discovered nodes for adding them as Contacts.

### Fixed
- Mgmt / UI - MAP; "Tiles Folder", fixed cosmetic issues fixed.
- Mgmt / Telemetry; when opening the Graphs overlay, now you can close it with a "back" button!
- Mgmt / GPS; fixed an issue where GPS could not be enabled/disabled properly.
- Mgmt / GPS; cosmetic issues fixed.
- MAP; Fix map scrolling bug: restrict map dragging to content area only
- I2C initialisation was broken - fixed!
- Indicator/RP2040; optimized the communication between RP2040 coprocessor and ESP32
- Indicator; fixed an issue where the bootsound was not working.
- Add SD persistence for UI preferences; Implement optional SD mirroring of UI prefs to /MCTerm/prefs.txt; NVS remains source of truth, SD provides backup across device erases; Add sync versioning to prevent stale data issues; Support both direct SD (T-Deck) and remote SD (SenseCap via RP2040); Live SD presence detection with automatic sync every 10 seconds; Include prefs: UI timeout, navigation, battery, contacts, NTP, sounds, map settings; Keyboard blink prefs only for T-Deck (conditional compilation)
- Cyrillic letters updated/fixed.

---

## [v0.9.6] prerelease for testers

 * Updated MeshCore Base to latest v1.12.0!

### Added
- Mgmt / UI -> Map; Added Map Show Zoom Buttons toggle (On/Off).
- Mgmt / UI -> Map; Added Map Show Navigation Buttons toggle (On/Off).
- Mgmt / UI -> Map; Added Map Default Follow Me toggle (On/Off).
- Mgmt / UI -> Map; Added Map Default Zoom Level setting (1-20).
- long Tap on Contacts Tab button; toggles between normal Contacts view and Discovered Nodes view to be able to add nodes when you do not activate in Mgmt / Channels the Auto Add Contacts option.
- Repeater Admin Menu; Implemented role-based gating (Guest/Admin) across Repeater Admin, Overview now visually disables admin-only buttons (ACL, CLI, Reboot, Passwords) when role isn’t Admin, and taps show a short popup instead of entering the screen. Device/Status/Telemetry overlays allow read-only viewing for Guest/RO, but write actions (edits/toggles/off/sync/reboot) are disabled visually and blocked on tap with a “RW/Admin required” popup.
- Indicator; (NEW IMAGE for RP2040 needed) Sound is now Supported & can be configured in Mgmt / UI -> Sound settings and will be processesd on the RP2040 coprocessor.
- Indicator; (NEW IMAGE for RP2040 needed) Added SenseCAP RP2040 SDCARD Support for remote SD access (read/write/list) does not yet offer direct services but will be used in future updates.
- Indicator; (NEW IMAGE for RP2040 needed) Added SenseCAP RP2040 Sensor Support for Temperature, Humidity, CO2, TVOC telemetry values (when RP2040 firmware is flashed with the new coprocessor image).
- MAP; tiles now can be donwloaded while you are connected to WiFi (when enabled in Mgmt / UI -> Map). If there is a SDCard present, it will automatically cache the tiles on the SDCard in the correct folder structure for offline use! (Indicator not yet supported!)
- Mgmt / UI -> Map; added info text about tile caching when WiFi is connected.
- Mgmt / UI -> Map; changed Map Tile folder structure from SD-Card.
- Mgmt / Messages; Addeed Auto Retry / Auto Reset Path / Direct Message Acks / Mark Delivered faster (like you know from the companion APP) but need to be setup separately because not connected to companion!
- MSGs / new button in Message "Reply" to quickly reply to the last DM or Channel message sender.

### Changed / Improved
- MAP; improved hop-count display in Contact detail view (shows "Direct" for 0 hops now and "1 hop", "2 hops", ... for others).
- Mgmt / Advert; neighbor adverts refactored to show more relevant information, and added the possibility to add discovered nodes as Contacts directly from the neighbor adverts list.
- Mgmt / Advert; changed button text "Advert Zero Hop" to "Advert - Direct"
- Mgmt / UI - moved Sound settings to Mgmt / UI for better grouping.
- Mgmt / Global - moved Mgmt / Admin into this menu for better grouping.
- Mgmt; changed some Texts&Buttons for better clarity (toggle, enabled/disabled)
- GUI; finally you can switch between BLE / WiFi or turn both completely off (without reboot!).
- Repeater Admin Menu / Advert; when disable both advert types, a warning popup (yes/no) is shown to inform the user that no adverts will be sent out anymore when accepted.
- MSGS; changed the top statusbar text from "msgs" to "Channels" and from "users" to "DMs" for better clarity.
- Contacts / soting; when you tap the contacts tab to cycle through sort orders, the view will automatically scroll to the top of the newly sorted list, making it much more user-friendly!
- Mgmt / CLI; fixed an issue while switching away from CLI breaks the touch.
- Mgmt / Stats; added the [>] buttons for the Radio section's Noise Floor, Last RSSI, and Last SNR lines in the Management > Stats view to see that this is clickable to open the Radio Stats overlay.

### Fixed
- Mgmt / CLI; fixed an issue after switching away from Mgmt / CLI to not be able to go back to the Mgmt / Overview due to a bug!
- Mgmt / GPS; GPS could not be disabled properly — fixed.
- MAP; fixed an issue where the MAP would not center on own GPS position when opening the MAP page.

### Removed
- Mgmt / UI -> Map; Removed overlay when there are no GPS Contacts with GPS coordinates available.

---

## [v8] — 2026-01-14

### Added
- Channels: Custom Command — configure via Mgmt → UI.
- Mgmt: Tele page — compact self-telemetry panel (VBAT, GPS, env values).
- Admin: System section — uptime, heap, PSRAM, flash/sketch usage, CPU, chip model/rev/cores, reset reason.
- Radio presets — predefined presets in Mgmt → Radio; selecting a preset applies settings and reboots.

### Changed / Improved
- Channels UI — redesigned layout; scroll-to-newest now marks all messages read.
- Mgmt / Log — layout updated to Channels-style with extended information.
- Mgmt / GPS — added RX/TX/Baud custom values.
- Battery press — short press toggles Volts ↔ Percent; long press still opens power popup; realtime duty-cycle display added.
- Contacts tab button — short press cycles filters (A–Z → Last heard → Last msg) and shows a 5s statusbar overlay; long press jumps to top.
- SenseCap — default text size increased (adjustable via ZOOM).
- Nick coloring — colored device names across UI (resets on reboot).

### Fixed
- Neighbor discovery — refactored and working.

---

## [v7] — 2026-01-11 (changes #2), [v6] — 2026-01-11 (changes #1)

### Fixed
- WiFi: connects but did not sync with App — fixed.
- Overscrolling could overdraw Back/Send buttons — fixed.

### Changed / Improved
- Top status bar: WiFi / BLE switching now triggers a reboot; setting is remembered.
- Page "Channels": unified message detail view — improved and fixed.
- Mgmt → Global: now shows the PublicKey and the first 2 letters of your PublicKey.
- Mgmt → BLE: added more information.
- Mgmt → WiFi: added more information (IP address, etc.).
- Mgmt → Log: completely renewed with more information.

### Added
- Contacts page: Tperm button — request telemetry from viewed contact.
- Contacts page: RT (RangeTest) button — sends "RangeTest - ACK?" automatically (customizable later).

---

## [v5] — 2026-01-11

### Added
- Firmware release v5 — merged firmware build for SenseCap Indicator D1Pro/D1L and LilyGO T-Deck Plus.
- Mail icon (unread indicator) in status bar: hidden = none; white = unread Channel; red = unread User.
- Battery icon popup — press the icon to show battery details.
- New RxLog — receive log screen.
- New Stats — on-device radio statistics screen.

### Changed / Improved
- Mgmt page: swipeable layout — more space and better overview.
- Channels page: swipeable views — Channel view vs User view (DMs).
- Contacts page: extra info/menus (WIP).
- Touch/display reaction: faster/more consistent UI response (WIP).
- Message details view: improved layout/behavior (WIP).
- WiFi password field: show/hide option.
- WiFi initialization + optimizations — improved stability.
- GPS settings visible (WIP).
- Map improvements.

---

## pre-version [2026-01-08]

### Fixed
- SenseCap RP2040 sensor telemetry → MeshCore telemetry — corrected LPP sensor types to avoid overflow; CO2 + TVOC index (plus temp/humidity) now map into proper MeshCore telemetry fields.

### Added
- ui-modern: Telemetry mini panel (Contact detail) — compact telemetry line in contact detail (voltage / temperature / humidity / CO2 / TVOC when available).
- Map: Tile view (T-Deck Plus) — tile view when SD card contains expected tile folder structure (if available).

### Changed / Improved
- ui-modern: Telemetry request behavior — changed to one-shot request when opening a contact; clear state shown: OK, NO ANSWER, or NO PERMISSION.
- Ping 0-hop improved — TRACE-based ping shows SNR there / SNR back and duration, or NO ANSWER after timeout.
