# 🧩 FFmpeg Patch Contributions

This repository contains my personal patch contributions to the [FFmpeg](https://ffmpeg.org) open-source project.  
The goal is to showcase my work on video codec internals — particularly HEVC, AV1, and related modules.

---

## 📌 HEVC YUV400 PCM Block Fix (Ticket #11551)

**Date Submitted:** Oct 18, 2025  
**Patch Title:** `[PATCH][HEVC] Fix PCM coding block length derivation for YUV400`  
**Status:** Pending review on FFmpeg mailing list  
**File:** `libavcodec/hevc/hevcdec.c`

### 🐞 Problem
When `chroma_format_idc == 0` (YUV400), FFmpeg incorrectly calculated PCM coding block length due to unnecessary chroma calculations, causing decode errors for YUV400 HEVC streams.

### 🧪 Solution
- Skip chroma calculation for YUV400 PCM blocks.
- Adjust byte skipping logic to match PCM block size for luma only.

### 🧠 Testing
- Generated a YUV400 HEVC sample.  
- Verified decoding succeeds without errors after applying the patch.

### 🔗 Reference
- [FFmpeg Trac Ticket #11551](https://trac.ffmpeg.org/ticket/11551)
- Submitted to ffmpeg-devel mailing list on Oct 18, 2025.

---

## 📂 Files in This Repo
- `0001-HEVC-Fix-PCM-coding-block-length-derivation-for-YUV400.patch` 
- `README.md` *(this file)*

---

## 👤 Author
**Sivasundaar P**  
📧 sivasundaar@gmail.com  
💻 Media Validation Engineer  
🎯 Areas of interest: Video codecs, FFmpeg, AV1, HEVC, media acceleration

