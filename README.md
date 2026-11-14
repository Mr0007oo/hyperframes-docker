# OpenShorts Multi-Arch Docker Images

Automated multi-architecture (`linux/amd64` and `linux/arm64`) Docker image builder and registry publisher for **[OpenShorts](https://github.com/mutonby/openshorts)**. 

This repository contains zero source code; instead, its sole purpose is to run GitHub Actions workflows that automatically pull, compile, and publish prebuilt container images directly to the **GitHub Container Registry (GHCR)** under `ghcr.io/mr0007oo/`.

---

## 📦 Container Image Mapping & Architecture

| Image Name (`ghcr.io/mr0007oo/...`) | Source Dockerfile | Build Context | Purpose |
| :--- | :--- | :--- | :--- |
| **`openshorts`** (Backend) | `./Dockerfile` | Root (`.`) | Runs the core Python FastAPI server, Whisper transcription engine, video download tools (`yt-dlp`), and AI moment scoring pipeline. |
| **`openshorts-frontend`** | `./dashboard/Dockerfile` | Dashboard (`./dashboard`) | Hosts the React web UI dashboard for reviewing clips, previewing captions, and managing exports. |
| **`openshorts-renderer`** | `./render-service/Dockerfile` | Root (`.`) | Handles subtitle rendering, video composition, and motion graphics automation using Remotion assets. |

---

## 📥 Pre-Made Docker Pull Commands

All published images are multi-architecture bundles supporting both standard servers (`linux/amd64`) and ARM64 environments (`linux/arm64` like Apple Silicon, AWS Graviton, or Oracle Cloud ARM). Docker will automatically pull the correct architecture for your host machine.

### 1. Backend Core Service
```bash
docker pull ghcr.io/mr0007oo/openshorts:latest
