PH's Archviz x AI ComfyUI Workflow (SDXL + Flux) - Dedicated to Architectural Imagery - v0.43_260223 cc-by-sa 4.0

Web:		https://www.paulhansen.de
Instagram:	https://www.instagram.com/paulhansen.design/
LinkedIn:	https://www.linkedin.com/in/ph3d/

Showcase: 	https://youtu.be/6aXJqRhjXo0
More Info:	https://www.reddit.com/r/comfyui/comments/1g1vaok/ai_archviz_with_comfyui_sdxlflux/

IF YOU WANT TO SUPPORT MY WORK (NO NEED TO, NO ADVANTAGE/DISADVANTAGE GAINED) you can donate at https://ko-fi.com/paulhansen


CHANGES
_______

v0.43_260223

- In case you get "Missing Nodes" messages with "If ANY retrn A else B [Microscope Icon]", "Float [Microscope Icon]", "Compare [Microscope Icon]", "Int [Microscope Icon]" -> On ComfyUI_windows_portable (recommended) install/update ComfyUI-Logic nodes (https://github.com/theUpsider/ComfyUI-Logic) through the Manager. Please be aware that these nodes have been ARCHIVED by the author.
- due to comfyui's node 2.0 implementation and incompatibility with rgthree FAST GROUP BYPASSER, this workflow works best with classic node (settings -> comfy -> Nodes 2.0 -> Modern Node Design (Nodes 2.0) -> "off"), otherwise groups have to be bypassed manually
- quality of life updates ensuring compatibility with latest ComfyUI (0.4.12)
- replaced with core nodes to reduce external dependencies
  - sipherxyz/comfyui-art-venture
  - melMass/comfy_mtb
  - jamesWalker55/comfyui-various
- removed
  - experimental section including automated inpainting, realtime sdxl previz stage and posed character control
  - optional preprocessors for depth, canny and pose alternatives

v0.37_251105

- quality of life updates ensuring compatibility with latest ComfyUI (0.3.68)

v0.30_250326

- quality of life updates ensuring compatibility with latest ComfyUI

v0.27_241114

- removed mixlabs nodes due to conflicting with other nodepacks and replaced FloatInputSliders with basic FloatInputs. Please be Aware, that you still can use Sliders, just be careful as it is not limited at the Moment, Will reimplement when possible again.

v0.23_241105

- initial release


MODELS used:
____________

	flux.dev gguf Q8_0.gguf
	juggernaut XI.safetensors

clip

	t5-v1_1-xxl-encoder-Q8_0.gguf
	clip_l.safetensors

ip-adapter

	CLIP.ViT-H-14-laion2B-s32B-b79K.safetensors
	ip-adapter-plus_sdxl_vit-h.safetensors

controlnet

	diffusers_xl_depth_full.safetensors
	diffusers_xl_canny_full.safetensors

sam2/florence2

	sam2_hiera_base_plus.safetensors
	Florence2-base

upscale

	4x-UltraSharp.pth


CUSTOM NODES used:
__________________

	GitHub - ltdrdata/ComfyUI-Manager
	GitHub - ltdrdata/ComfyUI-Impact-Pack
	GitHub - Fannovel16/comfyui_controlnet_aux
	GitHub - jags111/efficiency-nodes-comfyui
	GitHub - WASasquatch/was-node-suite-comfyui
	GitHub - EllangoK/ComfyUI-post-processing-nodes
	GitHub - BadCafeCode/masquerade-nodes-comfyui
	GitHub - city96/ComfyUI-GGUF
	GitHub - pythongosssss/ComfyUI-Custom-Scripts
	GitHub - ssitu/ComfyUI_UltimateSDUpscale
	GitHub - Suzie1/ComfyUI_Comfyroll_CustomNodes
	GitHub - cubiq/ComfyUI_IPAdapter_plus
	GitHub - Kosinkadink/ComfyUI-Advanced-ControlNet
	GitHub - theUpsider/ComfyUI-Logic
	GitHub - rgthree/rgthree-comfy
	GitHub - cubiq/ComfyUI_essentials
	GitHub - chrisgoringe/cg-image-filter
	GitHub - kijai/ComfyUI-KJNodes
	GitHub - kijai/ComfyUI-Florence2
	GitHub - kijai/ComfyUI-segment-anything-2
	GitHub - yolain/ComfyUI-Easy-Use

