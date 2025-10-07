# Copilot Instructions for JsNsf

## Project Overview
JsNsf is a JavaScript NSF (Nintendo Sound Format) player that emulates the 8-bit Nintendo's 6502 processor and APU sound chip to play chiptunes written for this system.

## Project Structure
- `cpu.js` - Emulates the 6502 CPU with instruction set implementation
- `mem.js` - Memory management
- `apu/` - Audio Processing Unit components (envelope, length counter, noise, pulse, triangle, resampler)
- `audio/` - Audio output handling (buffered audio node, step generator)
- `nsf.js` - NSF file format parser and player
- `nsfplayer.js` - Player orchestration
- `bankswitcher.js` - Bank switching for NSF files
- `clock.js` - Timing and clock management
- `util/` - Utility functions (math utilities)
- `scraps/` - Experimental/scratch code (not included in builds)

## Coding Style
- Use ES6 module syntax with `import`/`export default`
- Use JSDoc comments for type annotations (e.g., `@param {!Type}`, `@return {Type}`)
- Private class members use trailing underscore (e.g., `this.member_`)
- Use `const` for immutable values, avoid `var`
- Use template literals for string interpolation
- Follow camelCase for variables and methods
- Classes use PascalCase

## Build System
- Build uses Google Closure Compiler (via `java -jar`)
- `deps.pl` Perl script manages dependencies and generates makefiles
- Files marked with `//@` comments define build targets (e.g., `//@ output.compiled.js --checkTypes=warning`)
- Build output: `*.compiled.js` files
- Source maps: `*.srcmap` files
- Main build target: `nes.compiled.js`
- Run `make` to build the project
- Files in `scraps/` directory are excluded from builds

## Dependencies
- No npm/package.json - uses direct JavaScript imports
- Dependencies are managed through ES6 module imports
- Build system resolves dependencies via `deps.pl` script

## Testing
- No formal test framework currently in place
- Manual testing via `index.html` and `test4.html`

## Documentation
- Use JSDoc-style comments for functions and classes
- Document parameters with types (e.g., `@param {!Memory} mem`)
- Use `@private`, `@const`, `@type` annotations where appropriate
- Non-null types are prefixed with `!` (e.g., `{!Array<number>}`)

## Special Considerations
- This is a hardware emulation project - accuracy to NES/6502 behavior is important
- CPU instructions follow 6502 assembly instruction set
- Timing and cycle counting must be precise for audio playback
- Memory addresses are hexadecimal (e.g., `0x4015`)
- When making changes to CPU or APU, ensure emulation accuracy
