# 🏗️ PH's Archviz x AI ComfyUI Workflow (SDXL + Flux)

**Dedicated to Architectural Imagery**

**Author:** Paul Hansen  
**Version:** v0.37_251027  
**License:** CC BY-SA 4.0
---

![v0.43 Screenshot](https://github.com/paulh4x/AIxArchviz_ASSETS/blob/develop/img/Screenshot%202026-02-23%20095420.png)

---

### 🏆 Sponsorship

-   Please consider sponsoring me if you find the results of my work useful. A good way to keep code development open and free is through sponsorship.

-   [![BE A GITHUB SPONSOR ❤️](https://img.shields.io/badge/sponsor-30363D?style=for-the-badge&logo=GitHub-Sponsors&logoColor=#EA4AAA)](https://github.com/sponsors/paulh4x) . [![DIRECTLY SUPPORT ME VIA PAYPAL](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://www.paypal.com/paypalme/paulh4x) . [![SUPPORT ME ON KO-FI!](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/paulhansen)

---

## 📺 Showcase & Resources

* 🎥 **Showcase Video:** [https://youtu.be/6aXJqRhjXo0](https://youtu.be/6aXJqRhjXo0)
* 💬 **Original Reddit Thread:** [https://www.reddit.com/r/comfyui/comments/1g1vaok/ai_archviz_with_comfyui_sdxlflux/](https://www.reddit.com/r/comfyui/comments/1g1vaok/ai_archviz_with_comfyui_sdxlflux/)
* 🌐 **Web:** [https://www.paulhansen.de](https://www.paulhansen.de)
* 📸 **Instagram:** [https://www.instagram.com/paulhansen.design/](https://www.instagram.com/paulhansen.design/)
* 💼 **LinkedIn:** [https://www.linkedin.com/company/ph3d/](https://www.linkedin.com/company/ph3d/)

---

## 🎯 Overview

This ComfyUI workflow is a solution for transforming 3D architectural rendering elements like curvature/outline/toon/depth into photorealistic images using SDXL and Flux models. It's designed specifically for architectural visualization, allowing you to take basic 3D outputs (wireframes, colored meshes, normal passes, etc.) and generate high-quality, detailed architectural imagery through a multi-stage AI enhancement process.

The workflow leverages controlnets, masked detail transfer, and multiple AI models in sequence to progressively add detail and realism to your base images. It's a tool developed for technical artists who want to bridge the gap between low quality 3D rendering and final photorealistic output.

---

## ✨ Key Features

### Control & Flexibility

**Control over the desired outcome is mainly gained through:**
- **ControlNets in first stage:** Use depth, canny, or other controlnets to guide the initial generation
- **Masked detail transfer:** Define masks by prompt (e.g., "house, facade") to preserve and transfer details from your base image throughout the stages
- **Intelligent mask editing:** Masks are automatically adjusted to prevent detail bleeding onto areas like people placed with MaskEditor
- **Cherry-picking outputs:** Preview chooser allows you to select the best first-stage outputs before passing to the next stage
- **Flexible stage control:** Bypass stages you don't need, adjust settings with sliders and switches

### Multi-Stage Processing

The workflow uses various models in a row to add detail in each step:
1. **Stage 1 (SDXL):** Initial transformation using controlnets and your base image
2. **Stage 2 (Flux):** Detail enhancement and refinement
3. **Stage 3 (Flux):** Final detail pass and upscaling

### Input Compatibility

Depending on the models you use, the workflow can process:
- Outline renders
- Depth pass renders
- Any output that SDXL controlnet preprocessors understand
- Basic 3D Rendering outputs including screenshots

### Additional Features

- **People generation:** Proof-of-concept feature using MaskEditor to place Flux-generated people in your scene
- **Img2img mode:** Switch to img2img workflow with one button for more photorealistic base images
- **Adjustable denoising:** Control detail preservation vs. transformation in each stage

---

## ✅ This Workflow IS:

- **A potential replacement to many paid services** like image enhancement and upscaling
- **A tool developed for daily work** as a technical artist, assisting from previsualization to final image
- **Based on best intentions and latest findings** in AI-assisted architectural visualization
- **A flexible system** that can be adopted and modified to fit your specific needs
- **Part of a complete workflow** that still includes 3D environments, rendering software, and manual post-processing

---

## ❌ This Workflow IS NOT:

- **A masterpiece ComfyUI workflow never seen before** - it's a practical tool built from available components
- **Ultimate magic technology** that automatically produces award-winning images every time
- **A standalone solution** - it requires skill in 3D software, prompting, and ComfyUI knowledge
- **Optimized for all hardware** - it requires capable hardware (tested on RTX 4090)

---

## 🎯 Output Quality Depends On:

### Your 3D Skills
Your base image input is crucial. This workflow is designed for architecture-related imagery and assumes you have:
- Skills in a 3D environment (3ds Max, Blender, SketchUp, etc.)
- Ability to create appropriate outputs (normal passes, wireframes, colored meshes)
- Understanding of how to prepare renders for AI processing

### Your Prompting Ability
- Clear description of what you want
- Understanding of how prompts affect each stage
- Ability to use separated prompts for quick adjustments

### Your Hardware
- Basically, if you can run flux.dev, you can run this workflow
- Tested on GeForce RTX 4090
- Use more performant models and reduce resolution for lower-end hardware
- Optimization may follow in future releases

### Your Creativity & Knowledge
- Ability to adopt and edit the workflow to fit your needs
- Understanding of how ComfyUI and controlnets work
- Knowledge of which settings work for your specific scenario
- Willingness to experiment and iterate

---

## 📦 Models Used

### Main Models

**Flux:**
- `flux.dev gguf Q8_0.gguf`

**SDXL:**
- `juggernaut XI.safetensors`
- `realVisXL40_Turbo.safetensors` (only needed for "previz")

**Recommended models to try:**
- CrystalClearXL
- RealVisXL
- ProtoVision XL

### CLIP Models

- `t5-v1_1-xxl-encoder-Q8_0.gguf`
- `clip_l.safetensors`

### IP-Adapter

- `CLIP.ViT-H-14-laion2B-s32B-b79K.safetensors`
- `ip-adapter-plus_sdxl_vit-h.safetensors`

### ControlNet

- `diffusers_xl_depth_full.safetensors`
- `diffusers_xl_canny_full.safetensors`
- `thibaud_xl_openpose.safetensors` (optional, to be re-implemented with openpose-editor for posed people in future release)

### SAM2/Florence2

- `sam2_hiera_base_plus.safetensors`
- `Florence2-base`

### Upscale

- `4x-UltraSharp.pth`

---

## 🔧 Custom Nodes Required

**IMPORTANT:** It's recommended to install these ONE-BY-ONE and restart ComfyUI in between to prevent errors.

All of the following nodes are outstanding work and highly recommended:

- [ComfyUI-Manager](https://github.com/ltdrdata/ComfyUI-Manager) - ltdrdata
- [ComfyUI-Impact-Pack](https://github.com/ltdrdata/ComfyUI-Impact-Pack) - ltdrdata
- [comfyui_controlnet_aux](https://github.com/Fannovel16/comfyui_controlnet_aux) - Fannovel16
- [efficiency-nodes-comfyui](https://github.com/jags111/efficiency-nodes-comfyui) - jags111
- [was-node-suite-comfyui](https://github.com/WASasquatch/was-node-suite-comfyui) - WASasquatch
- [ComfyUI-post-processing-nodes](https://github.com/EllangoK/ComfyUI-post-processing-nodes) - EllangoK
- [masquerade-nodes-comfyui](https://github.com/BadCafeCode/masquerade-nodes-comfyui) - BadCafeCode
- [ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF) - city96
- [ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) - pythongosssss
- [ComfyUI_UltimateSDUpscale](https://github.com/ssitu/ComfyUI_UltimateSDUpscale) - ssitu
- [comfy_mtb](https://github.com/melMass/comfy_mtb) - melMass
- [ComfyUI_Comfyroll_CustomNodes](https://github.com/Suzie1/ComfyUI_Comfyroll_CustomNodes) - Suzie1
- [ComfyUI_IPAdapter_plus](https://github.com/cubiq/ComfyUI_IPAdapter_plus) - cubiq
- [comfyui-art-venture](https://github.com/sipherxyz/comfyui-art-venture) - sipherxyz
- [ComfyMath](https://github.com/evanspearman/ComfyMath) - evanspearman
- [comfyui-various](https://github.com/jamesWalker55/comfyui-various) - jamesWalker55
- [ComfyUI-Advanced-ControlNet](https://github.com/Kosinkadink/ComfyUI-Advanced-ControlNet) - Kosinkadink
- [ComfyUI-Logic](https://github.com/theUpsider/ComfyUI-Logic) - theUpsider
- [rgthree-comfy](https://github.com/rgthree/rgthree-comfy) - rgthree
- [ComfyUI_essentials](https://github.com/cubiq/ComfyUI_essentials) - cubiq
- [cg-image-picker](https://github.com/chrisgoringe/cg-image-picker) - chrisgoringe
- [ComfyUI-KJNodes](https://github.com/kijai/ComfyUI-KJNodes) - kijai
- [ComfyUI-DepthAnythingV2](https://github.com/kijai/ComfyUI-DepthAnythingV2) - kijai
- [ComfyUI-Florence2](https://github.com/kijai/ComfyUI-Florence2) - kijai
- [ComfyUI-segment-anything-2](https://github.com/kijai/ComfyUI-segment-anything-2) - kijai
- [image-resize-comfyui](https://github.com/palant/image-resize-comfyui) - palant
- [ComfyUI-Easy-Use](https://github.com/yolain/ComfyUI-Easy-Use) - yolain

---

## 🎁 Bonus Content

### Experimental Flux Inpaint by Mask

**To use this feature:**
1. Connect a mask to the respective node in the "mask area" (yellow typo)
2. Enable this process on the base cfg
3. Use a prompt for what you want to see

**Note:** This feature is a real experiment and does not always give the desired results.

---

## 📝 Version History

### v0.37_251105

- quality of life updates ensuring compatibility with latest ComfyUI (0.3.68)

### v0.30_250326

- quality of life updates ensuring compatibility with latest ComfyUI

### v0.27_241114

- Removed mixlabs nodes due to conflicts with other nodepacks
- Replaced FloatInputSliders with basic FloatInputs
- **Note:** You can still use Sliders, but be careful as they are not limited at the moment. Will reimplement when possible.

### v0.23_241105

- Initial release

---

## 🙏 Acknowledgements

This workflow would not be possible without the incredible work of the ComfyUI custom node developers listed above. Each of these developers has created outstanding tools that make complex AI workflows accessible and powerful.

**Special thanks to:**
- All the custom node developers whose work makes this workflow possible
- The ComfyUI community for continuous innovation and support
- Everyone who has provided feedback and suggestions

---

## ⚖️ License

**PH's Archviz x AI ComfyUI Workflow (SDXL + Flux)** © 2024 by Paul Hansen is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

---

## 📚 Additional Notes

### Target Audience

This workflow assumes you:
- Have a quick way to use or already know how to use a 3D environment (3ds Max, Blender, SketchUp, etc.)
- Can create the necessary outputs for the workflow
- Want to adopt some of these techniques into your own workflows
- Are willing to modify everything to fit your specific needs

### Workflow Philosophy

This is not a straightforward, one-click process. It's designed to be flexible and adaptable:
- Cherry-pick first stage outputs with a preview chooser
- Bypass stages you don't need
- Adjust settings for each specific use case
- Combine with your existing 3D and post-processing workflows

### Tips for Best Results

1. **Prepare your 3D output carefully:** Consider painting details directly onto render elements (e.g., vertical tiling lines on facade normal passes)
2. **Use appropriate controlnets:** Match your input type to the right controlnet preprocessor
3. **Adjust detail transfer amount:** Use sliders to control how much detail is preserved from your base image
4. **Experiment with denoise values:** Lower values in first stage for more photorealistic base images
5. **Let Flux add details:** Use stages 2 & 3 to progressively enhance your image
6. **Use masked detail transfer wisely:** Define clear masks for areas where you want to preserve architectural details

---

*This workflow represents a practical approach to AI-assisted architectural visualization, combining the power of multiple AI models with traditional 3D rendering workflows.*
