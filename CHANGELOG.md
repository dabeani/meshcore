# Changelog

All notable changes to this project.

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
