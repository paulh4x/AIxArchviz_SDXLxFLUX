PH's Archviz x AI ComfyUI Workflow (SDXL + Flux) - Dedicated to Architectural Imagery - v0.40_251027 cc-by-sa 4.0

Web:		https://www.paulhansen.de
Instagram:	https://www.instagram.com/paulhansen.design/
LinkedIn:	https://www.linkedin.com/company/ph3d/

Showcase: 	https://youtu.be/6aXJqRhjXo0
More Info:	https://www.reddit.com/r/comfyui/comments/1g1vaok/ai_archviz_with_comfyui_sdxlflux/

IF YOU WANT TO SUPPORT MY WORK (NO NEED TO, NO ADVANTAGE/DISADVANTAGE GAINED) you can donate at https://ko-fi.com/paulhansen


CHANGES
_______

v0.27_241114

- removed mixlabs nodes due to conflicting with other nodepacks and replaced FloatInputSliders with basic FloatInputs. Please be Aware, that you still can use Sliders, just be careful as it is not limited at the Moment, Will reimplement when possible again.

v0.23_241027

- initial release


MODELS used:
____________

	flux.dev gguf Q8_0.gguf
	juggernaut XI.safetensors
	realVisXL40_Turbo.safetensors (only needed for “previz”)

clip

	t5-v1_1-xxl-encoder-Q8_0.gguf
	clip_l.safetensors

ip-adapter

	CLIP.ViT-H-14-laion2B-s32B-b79K.safetensors
	ip-adapter-plus_sdxl_vit-h.safetensors

controlnet

	diffusers_xl_depth_full.safetensors
	diffusers_xl_canny_full.safetensors
	thibaud_xl_openpose.safetensors

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
	GitHub - melMass/comfy_mtb
	GitHub - Suzie1/ComfyUI_Comfyroll_CustomNodes
	GitHub - cubiq/ComfyUI_IPAdapter_plus
	GitHub - sipherxyz/comfyui-art-venture
	GitHub - evanspearman/ComfyMath
	GitHub - jamesWalker55/comfyui-various
	GitHub - Kosinkadink/ComfyUI-Advanced-ControlNet
	GitHub - theUpsider/ComfyUI-Logic
	GitHub - rgthree/rgthree-comfy
	GitHub - cubiq/ComfyUI_essentials
	GitHub - chrisgoringe/cg-image-picker
	GitHub - kijai/ComfyUI-KJNodes
	GitHub - kijai/ComfyUI-DepthAnythingV2
	GitHub - kijai/ComfyUI-Florence2
	GitHub - kijai/ComfyUI-segment-anything-2
	GitHub - palant/image-resize-comfyui
	GitHub - yolain/ComfyUI-Easy-Use

