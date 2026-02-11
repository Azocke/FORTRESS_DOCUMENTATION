# Fortress Security System v3.0

> **Status:** OPERATIONAL
> **Version:** 3.0.0-stable
> **License:** Proprietary / Commercial

---

## 🛡️ Vision & Philosophy

Fortress Security was built with a single mission: **Professional-Grade Security for Everyone.**

In an environment plagued by malicious actors and sophisticated exploits, standard anti-cheats often fall short. We designed Fortress not just as a script, but as a complete *architecture*. Our goal is to provide a defense-in-depth solution that is as beautiful as it is deadly to exploiters. We believe security should be silent, robust, and uncompromising.

---

## 📦 Installation

1.  **Download:** Obtain the latest build (`BuyerLoader.server.lua`) from your whitelisted download link.
2.  **Install:** Drag the loader script into `ServerScriptService`.
3.  **Configure:** Open `BuyerConfig.lua` inside the loader to set your preferences.
4.  **Run:** The system will automatically initialize at runtime.
    *   *Note:* The loader handles authentication and decrypts the latest core module.

---

## 🧩 Security Modules (Layers)

Fortress employs a multi-layered defense strategy. Technical details are obfuscated to maintain security integrity.

### 1. Prevention Layer
*   **IntegrityMonitor:** Validates runtime environment and critical functions.
*   **InstanceGuard:** Monitors `ServerScriptService` and `ReplicatedStorage` for unauthorized injections.
*   **BackdoorDetector:** Scans for known malicious patterns and heuristic anomalies.

### 2. Detection Layer
*   **PhysicsValidator:** Analyzes character movement for speed, flight, and teleport anomalies.
*   **RemoteSecurity:** Validates remote event traffic, protecting against spam and replay attacks.
*   **NetworkAnalyzer:** (Enterprise) Deep packet inspection for sub-frame timing attacks.
*   **HoneypotSystem:** Deploys fake remotes and values (`_G`, `shared`) to trap scanning tools.

### 3. Response Layer
*   **BanManager:** Handles persistent bans via DataStores with appeal support.
*   **TrustCore:** Assigns a dynamic Trust Score (0-100) to each player. Scores drop on violations; low scores trigger strict monitoring or kicks.

---

## ⚙️ Configuration (`BuyerConfig.lua`)

```lua
return {
    ADMIN_LIST = {12345678, 87654321}, -- UserIds of admins
    SAFE_MODE = false,                 -- If true, logs violations but does not punish
    KICK_THRESHOLD = 3,                -- Violations before kick
    BAN_THRESHOLD = 5,                 -- Violations before ban
    TRUST_PERSIST = true,              -- Save Trust Scores across sessions
    WEBHOOK_URL = "",                  -- Discord Webhook for logs
}
```

---

## 💻 Commands

Prefix: `/f` (e.g., `/f scan`)

*   `/f scan` - Force a full server-side integrity scan.
*   `/f safe` - Toggle Safe Mode on/off.
*   `/f ban <UserId>` - Manually ban a user (ignores Trust Score).
*   `/f unban <UserId>` - Revoke a ban.
*   `/f check <UserId>` - View a player's current Trust Score and violation history.
*   `/f logs` - Print recent detection logs to console.
*   `/f debug` - (Studio Only) Open the exploit testing menu.

---

## 🔧 Advanced & Troubleshooting

**Understanding Logs**
*   `[MATCH]` vs `[PRIORITY]`: Matches are standard signatures. Priority events (like `ANTICITIZEN ONE`) indicate high-threat behavior requiring immediate attention.
*   `[SCANNER]`: Indicates a player is likely using an exploit execution environment.

**Handling False Positives**
If valid gameplay mechanics (e.g., speed potions, vehicles) trigger detections:
1.  Check the console logs to identify the specific `VIOLATION_TYPE`.
2.  Adjust the corresponding threshold in `BuyerConfig.lua` (e.g., increase `MAX_SPEED`).
3.  Use `/f safe` to test changes without kicking players.

**Webhooks**
If Discord logs are missing:
*   Ensure `HttpService` is ON in Game Settings > Security.
*   Verify your Webhook URL is valid.

---

## ⚠️ Terms of Use & License Agreement

By purchasing and using Fortress Security, you agree to the following strictly enforced terms:

**1. No Redistribution**
*   You may NOT share, resell, or leak the loader or core scripts.
*   Sharing your license key or files will result in an immediate **License Revocation**.

**2. No Tampering**
*   You may NOT attempt to deobfuscate, reverse engineer, or modify the core logic.
*   Any attempt to break the obfuscation will trigger a self-destruct mechanism and revoke your license.

**3. Conduct Policy**
*   Licenses are privileged. We reserve the right to revoke access for:
    *   Scamming or fraud.
    *   Harassment or hate speech.
    *   Creating or distributing malware/exploits.
    *   Chargebacks (will result in a permanent blacklist).

**4. Payment**
*   Failure to adhere to the monthly subscription will result in temporary suspension.
*   Grace period: 7 days. Afterward, the loader will refuse to authenticate.

**Violation of these terms triggers an automatic HWID/IP blacklist across all Fortress-protected games.**

---

*Fortress Security © 2026. All Rights Reserved.*
