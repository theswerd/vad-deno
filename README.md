

# VAD on WASM!
![audio i made into an image](https://github.com/user-attachments/assets/5dc75a79-ecfb-4514-bfdd-eb5903ac6a55)

Package for Voice Activity Detection (VAD) on WASM so it can be used in Serverless Environments easily.

Built by the team at [Freestyle](https://www.freestyle.sh) for the amazing guys @ [Lilac Labs](https://www.lilaclabs.ai/) 🫶!

This package was heavily inspired by the work of [OzymandiasTheGreat](https://github.com/OzymandiasTheGreat) on [libfvad-wasm](https://github.com/OzymandiasTheGreat/libfvad-wasm/tree/main)

## Usage

```ts
const vad = new VAD();
await vad.init(); // Load the WASM module

const audioBuffer = /*Some Int16Array */

for (const isSpeech of vad.processAudio(audioBuffer)) {
    console.log(isSpeech);
}

vad.free(); // Free the memory
```

## Development

### Requirements

- Git
- Emcc (Emscripten)
- Deno

### Building

1. Install dependencies

    ```bash
    sh install.sh
    ```

2. Build the WASM module

    ```bash
    sh build.sh
    ```

3. Test it

    ```bash
    deno run -A examples/wav.ts your-audio-file.wav
    ```
