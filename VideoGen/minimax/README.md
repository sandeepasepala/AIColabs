# 🎬 FreeVideo (MiniMax H3) - Google Colab Notebook

[<img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab">](https://colab.research.google.com/github/syper4/AIColabs/blob/main/VideoGen/minimax/FreeVideo_MiniMax_H3.ipynb)

A complete, easy-to-use Google Colab notebook for running **[FreeVideo](https://github.com/FlashML-org/FreeVideo)** — a lightweight inference engine for **MiniMax H3** video generation based on **Video DeltaNet (VDN)**.

---

## 🌟 Overview

FreeVideo enables running the powerful **MiniMax H3** video model on consumer GPUs with as little as 8 GB of VRAM. It features:

- **Hardware-Adaptive Quantization**: Automatically switches to int8 (for consumer GeForce/RTX cards) or FP8 (for workstation/datacenter GPUs).
- **Video DeltaNet Hybrid Attention**: Extreme inference efficiency with 8-step base diffusion + 3-step refinement.
- **Dedicated Creative Workspace Web UI**: Built directly into ComfyUI (`?freevideo=launch`), allowing intuitive prompt-based video creation, duration adjustment, previewing, and history management.
- **Public Cloudflare Tunnel**: Generates a secure, public HTTPS URL so you can access the Web UI from any computer or mobile device without configuring ports or SSH.
- **Multimodal Generation**:
  - Text-to-Video (T2V)
  - Image-to-Video (I2V) with first and last frame keyframing
  - Audio references and community LoRA support

---

## 🚀 How to Run on Google Colab

1. Click the **[Open In Colab](https://colab.research.google.com/github/syper4/AIColabs/blob/main/VideoGen/minimax/FreeVideo_MiniMax_H3.ipynb)** button above.
2. Ensure you have selected a **GPU runtime**:
   - `Runtime` → `Change runtime type` → Select **T4 GPU** (or L4 / A100 for faster generation) → `Save`.
3. Run the cells step-by-step:
   - **Cell 1**: Verify GPU assignment and free disk storage.
   - **Cell 2**: Install system packages and Cloudflare tunnel client (`cloudflared`).
   - **Cell 3**: Clone the FreeVideo repository.
   - **Cell 4**: Run automated non-interactive setup (`./setup.sh --install-system-deps --yes --accept-model-license --plain`) to download MiniMax H3 weights and configure dependencies.
   - **Cell 5**: Start the FreeVideo server and Cloudflare tunnel. Click the generated **🚀 Open FreeVideo Web UI** link to access the studio.
   - **Cell 6 (Optional)**: Generate videos directly using the standalone CLI (`./freevideo generate`).

---

## 💻 Hardware Requirements

| Hardware | Recommended Config | Resolution | Speed (Est.) |
| :--- | :--- | :--- | :--- |
| **Colab T4 (15 GB VRAM)** | int8 / FP8 two-pass | 1344x768 / 960x544 | ~5–10 mins / clip |
| **Colab L4 / A100 (24–40 GB VRAM)** | FP8 full pass | 1344x768 | ~2–4 mins / clip |

---

## 🔗 References & Credits

- **FreeVideo Repository**: [FlashML-org/FreeVideo](https://github.com/FlashML-org/FreeVideo)
- **Video DeltaNet (VDN)**: [OpenVDN](https://github.com/OpenVDN)
- **Base Model**: [MiniMax H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)
