# Changelog

All notable changes to g.tec Altitude Assessment are documented here.
This project adheres to [Semantic Versioning](https://semver.org/).

## [1.0.0] — 2026

Initial public release.

### Added
- **Scope** — live EEG monitoring with a 1–30 Hz band-pass and a 48–52 Hz notch
  filter (monitoring only, not recorded).
- **VEP Checkerboard**, **AEP Oddball**, and **Resting state** paradigms, presented
  through g.tec Paradigm Presenter with UDP stimulus triggers merged into each
  recording.
- **Map** elevation picker (OpenTopoMap): location search, elevation lookup, named
  cursors, and CSV export. Recordings are auto-tagged with the selected location name
  and elevation.
- **Subject management** and **amplifier settings** (4- or 8-channel BCI Core, optional
  serial number) with full-screen / maximized window modes.
- Per-user Windows installer (no administrator rights required); recordings and settings
  persist alongside the application.

[1.0.0]: ../../releases/tag/v1.0.0
