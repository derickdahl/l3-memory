# MuseTalk Setup Log

**Date:** 2026-02-19  
**System:** Mac Studio (Apple M2 Ultra, 192GB RAM, macOS)  
**Goal:** Set up real-time audio-driven lip sync with MuseTalk or LivePortrait

## Progress

### Step 1: Repository Setup
- ✅ Created memory directory and setup log
- ✅ Successfully cloned MuseTalk repository
- ✅ Reviewed requirements.txt and README installation instructions

### Step 2: Python Environment Setup
- ✅ Created Python virtual environment using Python 3.14.2
- ✅ Activated virtual environment 
- ✅ Successfully installed PyTorch 2.10.0 with Apple Silicon support (MPS backend)
- ⚠️ Issue with requirements.txt: numpy==1.23.5 incompatible with Python 3.14
- ✅ Installed core dependencies: diffusers, transformers, gradio, librosa, opencv, etc.
- ✅ Installed mmengine successfully
- ⚠️ MMLab packages (mmcv, mmdet, mmpose) have pkg_resources compatibility issues with Python 3.14
- 🔄 Proceeding to test without MMLab packages first

### Step 3: Model Weights Download
- ✅ FFmpeg verified and working (version 8.0.1)
- ✅ Created Python script to download HuggingFace models
- ✅ Successfully downloaded MuseTalk V1.5, SD VAE, and Whisper weights from HuggingFace Hub
- ✅ Verified test image exists: ~/clawd/elle-headshot-straight-v1.png

### Step 4: Initial Testing
- ✅ PyTorch 2.10.0 installed with MPS (Apple Silicon) acceleration available
- ⚠️ MuseTalk inference scripts require mmpose (MMLab) which has Python 3.14 compatibility issues
- ⚠️ Some module imports failing due to missing MMLab dependencies

## Issues Encountered
- Python 3.14.2 compatibility issues with older pinned package versions
- MMLab packages (mmcv, mmdet, mmpose) failed to install due to pkg_resources compatibility issues
- huggingface-cli command not found in PATH, using Python API instead
- MuseTalk inference scripts fail due to missing mmpose dependency
- MoviePy import issues in app.py

## Analysis
MuseTalk has hard dependencies on MMLab packages (mmpose for pose detection) that are incompatible with Python 3.14. The recommended solution is to try LivePortrait as an alternative, as mentioned in the original task.

### Step 5: LivePortrait Alternative
- ✅ Successfully cloned LivePortrait repository
- ✅ Created separate Python virtual environment for LivePortrait
- ✅ Found macOS-specific requirements (requirements_macOS.txt)
- 🔄 Installing LivePortrait dependencies (simpler requirements, no MMLab dependencies)
- ✅ Building numpy, PyYAML, OpenCV, SciPy successfully (good sign for compatibility)

## Current Status Summary

### MuseTalk (Partially Working)
✅ **What's Working:**
- Repository cloned and environment set up
- PyTorch 2.10.0 with Apple Silicon MPS support installed
- All required model weights downloaded:
  - MuseTalk V1.5 (unet.pth, musetalk.json)
  - SD VAE (diffusion_pytorch_model.bin)
  - Whisper (pytorch_model.bin)
  - Face parsing models

❌ **What's Blocked:**
- Inference scripts fail due to missing mmpose dependency
- MMLab packages incompatible with Python 3.14

### LivePortrait (In Progress)
🔄 **Currently Installing:**
- Clean setup with dedicated virtual environment
- macOS-compatible requirements
- No problematic MMLab dependencies
- Building successfully so far

## Commands for Inference
**MuseTalk (blocked):** `bash inference.sh v1.5 normal`
**LivePortrait (pending):** To be tested once installation completes

---
*Last updated: 2026-02-19 22:36 PST*