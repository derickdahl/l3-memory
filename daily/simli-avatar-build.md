# Simli Avatar Build Progress

**Date:** 2026-02-20  
**Goal:** Build Elle's real-time avatar using Simli's LiveKit integration on Mac Studio

## ✅ Completed

### 1. Python Environment Setup
- Created virtual environment: `~/clawd/simli-avatar-venv/`
- Installed required packages:
  - `livekit-agents[openai]==1.4.2`
  - `livekit-plugins-simli==1.4.2`
  - `python-dotenv==1.2.1`

### 2. Project Structure
```
~/clawd/simli-avatar/
├── livekit-simli.py      # Main agent script
├── .env                  # Environment variables
├── requirements.txt      # Python dependencies
├── start-agent.sh        # Startup script (executable)
└── simli-avatar-venv/    # Virtual environment
```

### 3. Agent Script (`livekit-simli.py`)
- ✅ Proper imports and dotenv loading
- ✅ Environment variable validation
- ✅ OpenAI Realtime Model integration (voice: "alloy")
- ✅ Simli avatar configuration with API key and face ID
- ✅ Elle's personality instructions (L3-37 characteristics)
- ✅ Proper async entrypoint structure
- ✅ CLI runner setup

### 4. Environment Configuration (`.env`)
- ✅ Simli API key: `uwu28xd99i0ya4g0igw7u` (from credentials)
- ✅ Simli Face ID: `cace3ef7-a4c4-425d-a8cf-a5358eb0c427` (Tina preset)
- ⚠️ OpenAI API key: **MISSING**
- ⚠️ LiveKit credentials: **MISSING**

### 5. Startup & Setup Scripts
- ✅ `setup.sh` - One-time environment setup with credential checking
- ✅ `start-agent.sh` - Agent startup with validation
- ✅ Environment validation and prerequisite checks
- ✅ Clear error messages for missing credentials
- ✅ Executable permissions set
- ✅ Automatic credential detection and .env updating

### 6. Documentation
- ✅ `README.md` - Complete setup and usage guide
- ✅ `requirements.txt` - Pinned Python dependencies
- ✅ Progress documentation in `memory/simli-avatar-build.md`

## 🚨 Blockers

### 1. OpenAI API Key
**Status:** Not found in `~/.clawdbot/credentials/`  
**Need:** Valid OpenAI API key for Realtime Model  
**Action:** Derick needs to provide OpenAI API key

### 2. LiveKit Account & Credentials
**Status:** No LiveKit credentials found  
**Need:** 
- LIVEKIT_URL (wss://...)
- LIVEKIT_API_KEY
- LIVEKIT_API_SECRET

**Action:** Derick needs to:
1. Sign up at livekit.io
2. Create a "Video conference" Sandbox project
3. Copy the connection details to `.env`

## 🔄 Alternative: Direct Simli WebRTC

**Found:** Existing `~/clawd/elle-live-avatar/` project uses HeyGen with direct WebRTC  
**Approach:** Similar to Simli's direct compose/WebRTC endpoint  
**Status:** Could be explored as fallback if LiveKit setup is blocked

### Existing Architecture
```
User speaks → Web Speech API → Claude → HeyGen streaming → WebRTC video
```

### Potential Simli Alternative
```
User speaks → Web Speech API → Claude → Simli compose API → WebRTC video
```

## 🧪 Test Run Results

**Status:** Cannot test yet due to missing credentials  
**Ready when:** OpenAI + LiveKit credentials are provided

## 📋 Next Steps

1. **Immediate:** Get OpenAI API key from Derick
2. **Setup LiveKit:**
   - Create account at livekit.io
   - Create "Video conference" project
   - Add credentials to `.env`
3. **Test:** Run `./start-agent.sh` 
4. **Iterate:** Debug any issues and refine
5. **Fallback:** If LiveKit blocked, explore direct Simli WebRTC similar to existing HeyGen approach

## 🎯 Architecture Achieved

```
User speaks → LiveKit room → Simli avatar (lip sync) → Video output
Claude (Elle) → OpenAI Realtime → Simli → Video
```

**Components Ready:**
- ✅ Python environment with LiveKit + Simli plugins
- ✅ Agent script with proper Elle personality
- ✅ Simli avatar configuration
- ⚠️ Missing: OpenAI + LiveKit credentials

**Ready to deploy** once credentials are provided!