🌙 P3R: Moonlight

An adaptive handheld optimization framework for Persona 3 Reload

Optimize your journey through the Dark Hour.

P3R: Moonlight is an experimental, open-source project focused on improving the performance, frame pacing, image quality, and power efficiency of Persona 3 Reload on handheld gaming PCs.

Rather than relying on a universal collection of unverified tweaks, Moonlight aims to build a device-aware optimization framework that combines configurable performance profiles, benchmark-driven recommendations, reversible configuration management, and optional game-specific runtime modules.

Project status: Early development — architecture and feasibility validation.

Moonlight is not yet a validated performance optimizer. Device compatibility, configuration changes, and runtime modifications must be tested before being advertised as supported.

✨ Vision

The long-term goal is to make Persona 3 Reload easier to optimize across different handheld gaming devices without sacrificing reliability or user control.

Moonlight aims to provide:

🎮 Adaptive performance profiles tailored to different hardware capabilities and play styles.

📊 Benchmark-driven recommendations backed by reproducible measurements rather than guesswork.

🔋 Power-efficiency optimization that balances battery consumption, thermals, and performance.

🖥️ Device-aware configuration for different operating systems and handheld hardware.

🛠️ Reversible game configuration management with backups, validation, and restoration.

🧩 Optional runtime modules for carefully validated game-specific modifications.

🌐 A cross-platform architecture designed to support Windows and Linux-based handhelds over time.

🎯 Optimization Profiles

Moonlight is planned to include four primary profiles.

ProfileObjective⚡ PerformancePrioritize consistent frame pacing and a configurable frame-rate target.⚖️ BalancedBalance performance, image quality, and power consumption.🔋 Battery SaverReduce power consumption while maintaining an acceptable gameplay experience.👁️ Visual FidelityPreserve image quality while targeting a realistic level of performance.

These profiles describe optimization goals, not guaranteed results. Their actual settings and recommendations will depend on device capabilities, compatibility checks, and benchmark evidence.

Users should ultimately be able to customize their priorities instead of being restricted to predefined presets.

🧠 Core Design Principles

1. Measure before optimizing

No configuration change should be advertised as a performance improvement without appropriate testing.

Moonlight aims to record average frame rates, frame-time distributions, stutter events, graphics settings, hardware information, and other available measurements.

2. Safety first

The initial implementation will prioritize read-only inspection.

Configuration changes will require validation, backups, and a tested restoration mechanism. Runtime modifications will remain optional and disabled unless explicitly enabled.

3. Hardware independence

Moonlight will separate its shared optimization logic from platform-specific implementations.

The long-term goal is to support handheld gaming PCs running Windows and Linux, including SteamOS-based devices, where the necessary functionality can be implemented and validated.

Cross-platform compatibility is a design objective, not a claim of current support.

4. Modular architecture

The framework will be divided into independent components for device detection, profile evaluation, configuration management, benchmarking, and optional runtime integration.

This should make the project easier to test, maintain, and extend.

5. Honest compatibility reporting

Moonlight must distinguish between verified support, experimental functionality, unsupported configurations, and capabilities that have not yet been investigated.

Unknown information must remain unknown rather than being guessed.

🏗️ Planned Architecture

The initial architecture is organized into the following components:

ComponentResponsibilityMoonlight.CoreShared models, profile definitions, validation, and optimization policies.Moonlight.Platform.WindowsWindows hardware and operating-system capability detection.Moonlight.Game.P3RGame discovery, version identification, and P3R-specific integration.Moonlight.ConfigConfiguration inspection, backups, change tracking, and restoration.Moonlight.TelemetryCollection and normalization of benchmark measurements.Moonlight.BenchmarksBenchmark scenarios, comparisons, and performance reports.Moonlight.Runtime.AbstractionsInterfaces for optional runtime-modification modules.Moonlight.AppUser interface for profiles, diagnostics, and optimization management.Moonlight.TestsUnit, integration, and regression tests.

The initial release will prioritize the core libraries and a diagnostic command-line application. A graphical interface and runtime-modification framework will be developed as the architecture matures.

📈 Benchmarking and Telemetry

Moonlight is intended to evaluate more than average FPS.

Planned measurements include:

Average and percentile frame times.

Frame-time spikes and stutter frequency.

CPU and GPU utilization, where reliable telemetry is available.

Resolution and graphics configuration.

Power consumption and temperature, where supported.

Game version, driver version, test duration, and device power mode.

Benchmark comparisons should use repeatable scenarios and controlled settings.

Battery-life estimates will be treated as estimates unless validated using actual battery-discharge measurements. Results from desktop PCs will not be presented as handheld battery-life results.

🧩 Runtime Modification

Runtime modification is an optional, experimental part of Moonlight's long-term vision.

Potential research areas include:

Game-state inspection.

Runtime diagnostics.

Carefully validated gameplay or rendering hooks.

Compatibility-aware plugin interfaces.

Experimental optimizations for identified performance bottlenecks.

No specific runtime hook or engine-level optimization is assumed to work until it has been independently validated against the relevant game build.

The project will prioritize existing modding infrastructure where practical rather than unnecessarily duplicating established functionality.

🛠️ Technology Stack

The initial Windows development stack is planned around:

Language: C#

Framework: .NET

Platform integration: Windows-specific adapters, with future Linux support

Configuration: Versioned JSON schemas

Testing: Automated unit and integration tests

Version control: Git

Development workflow: Modular implementation, reproducible experiments, and benchmark-backed changes

The final framework version and Windows compatibility requirements will be confirmed during environment validation.

🗺️ Roadmap

Phase 0 — Feasibility research

Verify the development environment.

Identify Persona 3 Reload installation and configuration locations.

Investigate existing modding infrastructure.

Document compatibility assumptions and unknowns.

Phase 1 — Moonlight 0.1

Create the solution and project structure.

Implement profile models and schema validation.

Detect the host environment.

Discover the P3R installation and configuration directory.

Generate a read-only diagnostic report.

Add automated tests.

Phase 2 — Configuration management

Implement configuration inspection.

Add profile comparison and change previews.

Implement backups and restoration.

Detect configuration conflicts.

Phase 3 — Benchmarking

Define repeatable benchmark scenarios.

Import and normalize performance measurements.

Generate comparison reports.

Establish a desktop baseline.

Phase 4 — Adaptive optimization

Implement profile recommendation logic.

Introduce compatibility and evidence requirements.

Evaluate performance and power trade-offs.

Validate recommendations on real handheld hardware.

Phase 5 — Runtime research

Evaluate existing runtime-modification tools.

Prototype safe, version-checked integrations.

Measure candidate optimizations.

Add optional modules only when justified by evidence.

Phase 6 — Cross-platform expansion

Investigate SteamOS compatibility.

Implement platform-specific adapters.

Validate profiles on additional handheld devices.

Publish compatibility documentation.

Roadmap items represent intended work and are not claims that the functionality already exists.

🚀 Getting Started

Moonlight is currently in its early development stage. Installation and optimization instructions will be published once the initial implementation is ready.

Development prerequisites

The initial development environment is expected to include:

A compatible Windows development environment.

A supported .NET SDK.

Git.

A local installation of Persona 3 Reload on Steam for game-specific testing.

Planned first milestone

The first milestone is a read-only diagnostic application that can:

Detect the host system and available hardware information.

Locate the Persona 3 Reload installation when possible.

Identify the game's configuration directory.

Load and validate optimization profiles.

Generate a structured diagnostic report.

Complete these operations without modifying game files or saves.

Build instructions will be added after the solution structure and supported SDK version are established.

🧪 Compatibility and Testing

Compatibility will be tracked separately for each relevant game build, operating system, and optimization mechanism.

A successful launch does not automatically establish that a runtime module is safe or that an optimization improves performance.

Moonlight will aim to document:

Tested game and software versions.

Supported hardware and operating systems.

Known limitations and regressions.

Benchmark methodology and results.

Recovery and rollback procedures.

🤝 Contributing

Contributions will be welcome as the project becomes functional.

Potential contribution areas include:

Hardware and platform detection.

Profile validation and policy evaluation.

Benchmarking and telemetry.

Configuration parsing and restoration.

Compatibility research.

Automated tests and documentation.

Runtime-modification experiments backed by reproducible evidence.

Please include test results and relevant compatibility information when proposing changes that affect optimization behavior.

Contribution guidelines will be added before the first public development release.

⚖️ Disclaimer

P3R: Moonlight is an independent fan-made project and is not affiliated with, endorsed by, or sponsored by Atlus, Sega, or the developers of Persona 3 Reload.

Persona 3 Reload and its associated intellectual property belong to their respective rights holders.

Moonlight is intended to work with a legitimately obtained copy of the game. The project will not distribute copyrighted game assets or game executables.

Experimental runtime modifications may cause crashes, visual defects, or unexpected behavior. Users should maintain backups and follow the compatibility and recovery instructions provided with each release.

📜 License

The project license has not yet been selected.

A license will be added before public distribution. Until then, no open-source license should be assumed to apply.

P3R: Moonlight
The Dark Hour, optimized for anywhere. 🌙


