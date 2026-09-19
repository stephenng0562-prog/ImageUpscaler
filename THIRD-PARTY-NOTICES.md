# Third-party notices

The MIT licence on this project's own code covers `shell/`, `ui/`, `scripts/` and
the documentation. It does **not** cover the AI models, the enhancement engine
binary, or the libraries below.

**Three of these are non-commercial, and that restriction binds the packaged app
as a whole.** They are marked.

## AI models and engines

### Real-ESRGAN — the Natural and Cartoon styles
**BSD 3-Clause** · Copyright (c) 2021, Xintao Wang
<https://github.com/xinntao/Real-ESRGAN>

### Real-ESRGAN ncnn Vulkan — the engine that runs them
**MIT** · Xintao Wang
<https://github.com/xinntao/Real-ESRGAN-ncnn-vulkan>

### 4x-UltraSharp — the Max Detail style
**CC BY-NC-SA 4.0 — attribution required, NON-COMMERCIAL, share-alike**
Kim2091 · <https://openmodeldb.info/models/4x-UltraSharp>
The ncnn conversion comes from Nenotriple/gimp_upscale.

### GFPGAN — the Natural portrait style
**Apache 2.0, with a NON-COMMERCIAL restriction inherited from StyleGAN2**
TencentARC · <https://github.com/TencentARC/GFPGAN>

### CodeFormer — the Strong repair portrait style
**S-Lab License 1.0 — NON-COMMERCIAL use only**
sczhou · <https://github.com/sczhou/CodeFormer>

### YuNet — face detection
**MIT** · Copyright (c) 2020 Shiqi Yu · <https://github.com/opencv/opencv_zoo>

### ncnn — the neural network runtime
**BSD 3-Clause** · Copyright (C) 2017 Tencent · <https://github.com/Tencent/ncnn>

## Libraries bundled into the executable

| Component | Licence | Used for |
|---|---|---|
| ONNX Runtime | MIT | Running the face models on the processor |
| OpenCV (headless) | Apache 2.0 | Detection, alignment and paste-back |
| Pillow | MIT-CMU | Reading, resizing and writing every image |
| NumPy | BSD 3-Clause | Array maths |
| pywebview | BSD 3-Clause | Hosting the interface in a native window |
| Bottle | MIT | Serving the interface files over loopback |
| Python.NET | MIT | Bridging Python to the Windows window |
| clr-loader | MIT | Loading the .NET runtime for the above |
| cffi / pycparser | MIT | A dependency of clr-loader |

## Typeface

### Inter
**SIL Open Font License 1.1** · Rasmus Andersson · <https://rsms.me/inter/>
Shipped as `ui/assets/fonts/InterVariable.woff2`. The OFL permits bundling and
redistribution; the font is not sold and is not used as the name of this work.

---

Full licence texts for everything above are in [`licenses/`](licenses/), and at
the links given.

That directory also carries texts for SwinIR and CustomTkinter, which nothing in
this build uses. They are kept rather than pruned: covering more than you ship is
the safe direction to err in, and a licence file costs nothing to carry.
