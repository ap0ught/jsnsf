# JsNsf

JsNsf is a JavaScript NSF (Nintendo Sound Format) player. It emulates the 8-bit Nintendo's 6502 processor and APU sound chip and can play chiptunes written for this system.

## Features

- **6502 CPU Emulation**: Full implementation of the 6502 processor instruction set
- **APU Sound Chip**: Accurate emulation of the NES Audio Processing Unit including:
  - Pulse channels (2)
  - Triangle channel
  - Noise channel
  - Envelope generators
  - Length counters
- **Bank Switching**: Support for NSF bank switching (including FDS)
- **Web-based Player**: Browser-based interface for loading and playing NSF files

## Quick Start

### Playing NSF Files

1. Open `index.html` in a web browser
2. Click "Choose File" and select an NSF file
3. Click "load" to start playback
4. Use the channel checkboxes to enable/disable individual audio channels

### Building from Source

This project uses Google Closure Compiler for building. See [README.dev](README.dev) for detailed development instructions.

```bash
# Build the project
make
```

This will generate `nes.compiled.js` which is used by `index.html`.

## Project Structure

```
.
├── cpu.js              # 6502 CPU emulator
├── mem.js              # Memory management
├── apu/                # Audio Processing Unit components
│   ├── envelope.js     # Envelope generator
│   ├── lengthcounter.js # Length counter
│   ├── noise.js        # Noise channel
│   ├── pulse.js        # Pulse channels
│   ├── triangle.js     # Triangle channel
│   └── resampler.js    # Audio resampling
├── audio/              # Audio output handling
│   ├── bufferedaudionode.js # Buffered audio playback
│   └── stepgeneratornode.js # Step-based waveform generation
├── nsf.js              # NSF file format parser
├── nsfplayer.js        # Player orchestration
├── bankswitcher.js     # Bank switching implementation
├── clock.js            # Timing and clock management
└── util/               # Utility functions

```

## Upstream Repository

This is a fork of [shicks/jsnsf](https://github.com/shicks/jsnsf). See [UPSTREAM_ISSUES.md](UPSTREAM_ISSUES.md) for tracking of upstream issues and branches.

## Known Issues

- Some NSF files may not play correctly due to CPU emulation accuracy
- Some files may produce "Cannot write to immediate value" errors

See [UPSTREAM_ISSUES.md](UPSTREAM_ISSUES.md) for more details.

## Contributing

Contributions are welcome! Please see:
- [CONTRIBUTION_GUIDE.md](CONTRIBUTION_GUIDE.md) for contribution guidelines and upstream relationship
- [README.dev](README.dev) for development setup instructions

## License

See the original repository for license information.

