# video2audio_gui

A small desktop GUI for extracting audio tracks from video files with FFmpeg.

## Status

This repository is in maintenance-only / archival-preparation mode. The current implementation is kept as a compact reference rather than as an actively developed application.

## Features

- Single-file and batch conversion
- Recursive folder scanning with configurable file patterns
- MP3, M4A/AAC, WAV, FLAC, OGG/Vorbis, and Opus output
- CBR/VBR controls where supported by the selected codec
- Mono/stereo and sample-rate selection
- Optional start time and duration
- Parallel batch jobs
- Optional preservation of the source directory structure

Supported input extensions are currently `.mp4`, `.m4v`, `.mov`, `.mkv`, and `.webm`.

## Requirements

- Python 3
- FFmpeg available on `PATH`
- FreeSimpleGUI (preferred), or a compatible PySimpleGUI v4 installation

The application first tries `FreeSimpleGUI` and falls back to `PySimpleGUI`. A local `third_party/` directory is also added to the import path when present.

## Run

```bash
python video2audio_gui.py
```

The GUI reports whether FFmpeg can be found before conversion.

## Validation scope

CI performs syntax compilation of the Python source and validates GitHub Actions workflow syntax. Media conversion itself depends on the local FFmpeg build/codecs and a graphical desktop environment, so it is intentionally not represented as a full end-to-end CI guarantee.

## Notes

- Existing output files are skipped unless **Overwrite existing files** is enabled.
- WAV and FLAC ignore bitrate/VBR controls.
- M4A uses FFmpeg's built-in AAC encoder.
- Available encoders can vary between FFmpeg distributions.

## License

MIT. See [LICENSE](LICENSE).
