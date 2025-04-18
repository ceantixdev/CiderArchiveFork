Cider seems to have a bug when compiling on Linux (The only option for accessing Cider V1 as the original release is archived). This patch should fix the problem for compiling from source. If you don't trust my repo I don't blame you, make the same changes below in the archive to patch it yourself.

src/main/base/browserwindow.ts:1303

let pcmData = Buffer.from(interleave16(bitratechange(Int16Array.from(newaudio[0], (x) => convert(x))), bitratechange(Int16Array.from(newaudio[1], (x) => convert(x)))).buffer);

src/main/plugins/raop.ts:329

this.airtunes.circularBuffer.write(Buffer.from(Int8Array.from(result.outbuffer)));

To compile from source check out their [docs](https://cider.gitbook.io/welcome-to-gitbook/docs/3.legacy-docs/2.compilation]https://cider.gitbook.io/welcome-to-gitbook/docs/3.legacy-docs/2.compilatio).

For anyone with NodeJS already installed it should just be these two commands for x86-64-bit systems.
```
npm install --force
```
```
npm run dist -l --x64
```
