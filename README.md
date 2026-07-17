# g.tec Altitude Assessment

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Platform](https://img.shields.io/badge/platform-Windows%2010%20%2F%2011%20(x64)-lightgrey)
![License](https://img.shields.io/badge/license-Free%20for%20private%20use-green)

**Outdoor, EEG-based assessment of evoked-potential biomarkers (AEP, VEP) at
different elevations**, using a g.tec **BCI Core-4** or **BCI Core-8** amplifier.

Altitude Assessment is a touch-friendly, full-screen Windows application for the
field. Pick a location on a map, read off its elevation, then record auditory
(AEP) and visual (VEP) evoked potentials, or a resting-state EEG — each recording
automatically tagged with the subject, location, and altitude at which it was made.

> **This software is free for private use.** See [License](#license) below.

---

## Download & install

Everything you need is in the **[latest release](../../releases/latest)**.
Two installers are provided; **run both — the order does not matter** — and the
app is ready to use.

| Installer | What it does |
|-----------|--------------|
| `ParadigmPresenterInstaller_x64.msi` | Installs the g.tec **Paradigm Presenter**, the stimulus-presentation engine used to run the VEP / AEP / resting-state paradigms. |
| `AltitudeAssessment-Setup-1.0.0.exe` | Installs the **Altitude Assessment** application itself. |

### Steps

1. Open the **[latest release](../../releases/latest)** and download both files.
2. Run `ParadigmPresenterInstaller_x64.msi` and `AltitudeAssessment-Setup-1.0.0.exe`
   (either order).
3. Launch **g.tec Altitude Assessment** from the Start menu or desktop shortcut.

The application installs **per-user** (to `%LocalAppData%\Programs\AltitudeAssessment`)
and requires **no administrator rights**.

---

## System requirements

- **Windows 10 or 11, 64-bit**
- **g.tec BCI Core-4** or **BCI Core-8** amplifier (connects over **Bluetooth Low
  Energy**) — required to acquire and record signals
- A **Bluetooth LE** adapter
- **Audio output** (for the AEP paradigm) and a suitable **display** (for the VEP
  paradigm)
- An **internet connection** — required only by the *Map* elevation picker; every
  other feature works fully offline

---

## Features

- **Scope** — live signal monitoring with a 1–30 Hz band-pass and a 48–52 Hz notch
  filter, for checking electrode contact and signal quality. *(Monitoring only — not
  recorded.)*
- **VEP Checkerboard** — visual evoked potential paradigm (checkerboard reversal).
- **AEP Oddball** — auditory evoked potential paradigm (target / non-target tones).
- **Resting state** — timed eyes-open/-closed resting recording.
- **Map** — an interactive OpenTopoMap picker: search or click a location, read its
  elevation, and drop named "cursors" so each recording is tagged with the place and
  altitude. Saved locations can be exported to CSV.
- **Settings** — manage the subject list, choose 4- or 8-channel acquisition (with an
  optional amplifier serial number), and pick full-screen or maximized window mode.

Stimuli are presented through g.tec Paradigm Presenter, which sends stimulus-onset
triggers to the application over UDP; those triggers are merged into the recording so
each sample is aligned with the stimulus that produced it.

---

## Using the app

1. **Select a subject** in the left-hand panel (add or remove subjects under
   **Settings**).
2. *(Optional)* Open **Map**, choose your location, and set a named cursor — this
   stamps the location name and elevation onto the recordings that follow.
3. Open **Scope** to verify signal quality.
4. Run **VEP Checkerboard**, **AEP Oddball**, or **Resting state**. Press the large
   **Start** button to begin and **Stop** to end; press **Esc** to close the app.

### Where recordings and settings go

All output is written next to the executable, under
`%LocalAppData%\Programs\AltitudeAssessment\`, so it persists across runs:

| Path | Contents |
|------|----------|
| `data\vep\`, `data\aep\`, `data\resting\` | Recorded EEG as CSV, e.g. `vep_<subject>_<location>_<elevation>.csv` |
| `subjects.json` | Subject list |
| `amp_config.json` | Amplifier & window settings |
| `map_markers.json`, `map_location.json` | Saved map cursors and last map view |

---

## Troubleshooting

- **The map shows "No internet connection."** The map picker needs internet to load
  tiles and look up elevation; the paradigms and scope do not. Reconnect and reopen the
  Map page.
- **The amplifier isn't found.** Make sure the BCI Core is powered on and in range, and
  that Bluetooth is enabled. If you run more than one amplifier nearby, set the specific
  serial number under **Settings → Amplifier**. Also confirm the channel count (4 or 8)
  matches your device.
- **No stimuli appear when starting a paradigm.** Confirm the Paradigm Presenter
  installer (`ParadigmPresenterInstaller_x64.msi`) was run.

---

## License

This software is **free for private, personal, non-commercial use**. All rights are
reserved by g.tec medical engineering GmbH. See the full terms in [LICENSE](LICENSE).

> **Not a medical device.** g.tec Altitude Assessment is intended for research and
> educational use only. It is **not** intended for the diagnosis, treatment, or
> prevention of any disease or medical condition.

Bundled third-party components (e.g. Qt / PySide6 and other open-source libraries)
remain under their own respective licenses.

---

## Support

For questions about the g.tec BCI Core amplifiers or this application, visit
[www.gtec.at](https://www.gtec.at).

© 2026 g.tec medical engineering GmbH. "g.tec", "BCI Core", and "Paradigm Presenter"
are trademarks of g.tec medical engineering GmbH.
