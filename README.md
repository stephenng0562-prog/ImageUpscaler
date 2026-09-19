# Image Upscaler & Enhancer

Makes your photos bigger and clearer, on your own computer. No internet, no
accounts, nothing uploaded.

Point it at a small or blurry picture and it rebuilds the detail using AI models
that run on your own machine.

## What it does

|              | **One** photo  | **Many** photos          |
|--------------|----------------|--------------------------|
| **Photo**    | Enlarge 4×     | Enlarge a whole folder   |
| **Portrait** | Repair a face  | Repair a folder of faces |

**Photo** is for scenery, objects, buildings and game screenshots. **Portrait**
is for pictures of people, and repairs faces specifically. All four combinations
work, so an album of family photos can be restored in one run.

### Styles, which are also the speed control

Each style shows an estimate worked out from your actual photo, before you
commit to the wait.

For photos:

- **Natural** — the all-rounder. Keeps texture looking like texture.
- **Cartoon** — for drawings, anime and illustration. Roughly two and a half
  times quicker than the other two, because its model is much smaller. It will
  make a real photograph look drawn.
- **Max Detail** — pushes sharpness furthest. Excellent up close, and it can
  over-crisp a soft background.

For portraits:

- **Natural** — cleans a face up without changing who it looks like. The safe
  choice for family photos.
- **Strong repair** — rebuilds much more detail, with a slider running from
  faithful to the original through to full repair. Can drift from the real face
  at full strength.

### Size

Every style enlarges four times. The size control offers two and three times as
well, which is the same four-times render scaled back down afterwards. It
changes the dimensions of what you save, not how long the job takes.

## Getting started

1. Download the [zip](https://github.com/stephenng0562-prog/ImageUpscaler/releases/latest) from the releases page and unpack it anywhere you like.
2. Open the folder and run **ImageUpscaler.exe**.

The first time it opens, the app asks whether you would like a shortcut on your
Desktop. It asks once, whichever way you answer. If you say no and change your
mind later, run **Create desktop shortcut.bat** from the same folder.

Keep the folder together and move it as a whole. The app reads its engines and
models from the files sitting beside the executable.

The app is not code-signed, so the first launch may bring up a blue "Windows
protected your PC" panel. Choose **More info**, then **Run anyway**. That notice
means nobody has paid for a signing certificate, not that anything is wrong.

There is a **Help** page inside the app covering the three steps, the styles,
comparing before and after, and the keyboard shortcuts.

## What you need

Windows 10 or 11, 64-bit. A Vulkan-capable graphics card for enlarging —
Portrait works without one, on the processor. The Edge WebView2 runtime, which
is already part of Windows 11.

## Your photos stay on your computer

Nothing is uploaded, there is no telemetry, and there are no accounts. The app
has no code capable of sending a file anywhere.

The interface is a web page, so the app runs a small server on 127.0.0.1 to hand
that page to its own window. That address is your own machine and nothing else
can reach it; no photo passes through it.

Do not take our word for it. The source is public, and the About page inside the
app gives you the command to search it with — there is a button beside it that
copies the command so you can paste it into a terminal yourself.
[PRIVACY.md](PRIVACY.md) sets out the whole of it.

One thing worth saying plainly: enlarging a photo means inventing detail that
was never captured. Usually that reads as sharpness. Sometimes it reads as a
face that is not quite the right face. Keep your originals.

## Licence: please read before you reuse this

This project's own code is MIT ([LICENSE](LICENSE)).

The AI models are other people's work and are not covered by that. Three of them
— CodeFormer, 4x-UltraSharp, and GFPGAN by way of StyleGAN2 — are released for
non-commercial use only, and that restriction binds the packaged app as a whole.
Use it on your own photos freely. Do not sell it, sell its output, or include it
in a commercial product.

**Do not publish this app to an app store, download portal or software
directory,** free or paid, and do not present it as your own work. To share it,
link people to the official release page.

The name "Image Upscaler & Enhancer" and the app icon are reserved. The MIT
licence grants copyright permissions and says nothing about the name a thing
ships under. Fork the code freely; release the result under a different name.

Every component, its author and its terms are in
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md). Full licence texts are in
[`licenses/`](licenses/).

The app comes with no warranty of any kind.
