---
type: resume-bullet-library
created: 2026-10-14
updated: 2026-10-14
tags: [type/resume-bullet-library]
---

# Bullet Library

Full pool of resume bullets per role, including ones cut from `Resume (Robotics+Ai).tex` for space.
`Resume (Robotics+Ai).tex` only has room for ~4 bullets per recent role — this file keeps the rest
so future tailoring (a different job posting, a longer CV, a LinkedIn update) doesn't require re-mining
`WorkUpdates.md` from scratch.

Convention (per `.github/skills/resume-version-manager/`): when a bullet is replaced in the `.tex`, move
it here instead of deleting it — dated, with the keywords it demonstrates for ATS matching.

## Porsche Engineering Services GmbH — Working Student, Humanoid Robotics, Development & Validation
Apr 2026 -- Present | Stuttgart, Germany

### Currently in resume (as of 2026-10-14)
- Deployed and validated an NVIDIA cuVSLAM + nvblox perception-localization stack on Unitree Go2/G1 (Jetson Orin NX, RealSense D435i), resolving DDS, TF-tree, and domain-ID conflicts to sustain 30 Hz visual odometry and real-time 3D reconstruction.
- Unified Go2 and G1 onto a single arm64 YOLOv8/TensorRT detection pipeline (Isaac ROS), fixing build, QoS, and runtime defects to reach real-time detections at ~24 Hz on embedded Jetson hardware.
- Designed `perception_service`, a SOLID-refactored ROS 2 package converting 2D detections into 3D object poses at 30 Hz with full unit-test coverage, enabling downstream navigation and manipulation.
- Re-architected the robot audio stack: unified text-to-speech into a shared cross-robot scheduler and shipped a swappable ASR backend (Nemotron) with VAD-based turn detection and wake-word gating.

### Cut 2026-10-14 (replaced — generic, pre-dated most real work)
- Developed and integrated robotics software for Unitree Go2 (quadruped) and G1 (humanoid) robots using ROS 2, NVIDIA Isaac ROS, and Jetson, enabling perception, localization, and navigation capabilities.
- Built and maintained Docker-based deployment workflows for embedded robotics applications, debugging complex middleware, networking, dependency, and containerization challenges across development and production environments.
- Integrated and evaluated hardware components including cameras, audio systems, and onboard compute, while contributing to simulation, visualization, and real-world robot validation.
- Collaborated with cross-functional engineering teams through code reviews, technical documentation, and feature validation, delivering production-ready robotics software and deployment improvements.

### Not currently used — additional pool (pull from here when tailoring)
*Keywords each covers noted in parens for ATS matching.*

- Containerized DimensionalOS SLAM/Nav as a Docker Compose service alongside the existing cuVSLAM/NVBlox stack, with map persistence and auto-relocalization (fitness 0.674) validated end-to-end on hardware. (Docker, SLAM, DevOps, map persistence)
- Added a `perception_detection_metrics` ROS 2 package publishing live per-class confidence/rate diagnostics through `robot_gateway` to the frontend over WebSocket. (observability, metrics, ROS 2, WebSocket)
- Root-caused a recurring `tensor_rt_container` crash traced to a stale cached TensorRT engine silently reused across CUDA/TensorRT version changes. (debugging, TensorRT, root-cause analysis)
- Diagnosed and resolved a TF-tree conflict (cuVSLAM vs. robot_state_publisher) and a DDS domain-ID mismatch making Nav2 invisible to cuVSLAM, restoring healthy costmap publishing. (ROS 2, DDS, TF, Nav2)
- Fixed a FastDDS shared-memory transport bug silently blocking RViz image display on both G1 and Go2. (debugging, DDS, RViz)
- Hardware-verified a full G1 TTS redesign: replaced unreliable onboard RPC with PCM streaming, resolving a wire-format bug (stream_id sent as JSON number vs. firmware-expected string); 312 tests passing. (C++, audio, firmware debugging, testing)
- Shipped a VAD-gated wake-word turn-detection state machine (Silero VAD) governing when the robot responds to speech. (audio, VAD, state machines)
- Evaluated Qwen3-ASR-1.7B vs. Nemotron 3.5 ASR for GPU memory footprint (~8 GB vs. ~1.2 GB) on embedded hardware and led the decision to standardize on Nemotron. (ASR, model evaluation, embedded constraints, decision-making)
- Led an architecture split of the perception-detection interface per code review, separating the swappable YOLOv8 backend (`amor-deploy`) from the stable `perception_service` wrapper (`amor-robot`). (software architecture, SOLID, code review)
- Root-caused a TensorRT engine-build slowdown (confirmed via `tegrastats` the GPU was idle) and built an automatic workaround using raw TensorRT bindings, cutting engine build time to ~7 minutes with no manual steps. (TensorRT, CUDA, performance debugging)

## Other roles

Current resume bullets for Student Assistant (SIR Lab), Student Assistant (Construction Robotics), and
Research Intern (IIITDM Kancheepuram) are unchanged since the last extraction into the vault — see
`Master Resume.md` and `01_Profile/Resume History` for their full history. Not duplicated here to avoid
two sources of truth; add a section here if/when those roles also need a cut-bullet pool.
