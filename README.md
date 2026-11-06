# Benchmark images for ARMSX3 PRs (vertex fetch specialization, early submit)

Charts and screenshots referenced from the pull requests that follow ARMSX2/ARMSX3#230. This branch holds only
these images; it is not meant to be merged.

- Device: Retroid Pocket 6 (Snapdragon 8 Gen 2, Adreno 740), Android 13.
- Builds: ARMSX3 1.6.4 (482d35b6a), and 1.6.4 + the core commits of both PRs. Both builds also carry the include fix
  (#231) and a test-only frame-time log (FTIME/VKSTAT lines).
- Method: savestate booted through the external-launch intent; the arm is chosen by the per-title database file;
  every run starts with the device below 60 C; 19 s of scripted combat; only 5 s windows at full scene are compared;
  one warm-up run per arm, then the arms in a mirrored order (1.6.4, off, A, B, A+B, A+B, B, A, off, 1.6.4).
- Charts: FPS per 5 s window, GPU busy (KGSL), CPU used by the emulator per thread class (from /proc, whole run),
  frames over 50 ms, frame time per 1,000 draws, busiest thread.
- Screenshots: RPCS3's performance overlay is on in these sessions, the same in every arm.

Files:
- `tod_turnip_W.png`, `tod_overlay_W.jpg`, `tod_pair_W.jpg`: Tools of Destruction, Turnip (Mesa 26.3.0-devel).
- `tod_turnip_U.png`: the same on Turnip, an earlier session without CPU sampling.
- `tod_qcom_Q.png`, `tod_overlay_Q.jpg`: Tools of Destruction, stock Qualcomm driver.
- `qfb_turnip_V.png`: Quest for Booty, Turnip (PR build only).
