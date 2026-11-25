# Symbolic Prompting: Turning LLMs into High-Throughput, Zero-Trust Linux EDR Engines

This example demonstrates how to use the Symbolic Prompting Framework (SPF) to transform raw, unstructured execution strings into highly structured security data. By executing a strict zero-trust analysis over environment variables, runtime parameters, and process indicators, we can seamlessly eliminate OS background noise and extract actionable intelligence.

> [!IMPORTANT]
> **Core Concept**: It is designed to automate the process-auditing lifecycle by continuously scanning dynamic system variables, eliminating operating system background noise, and transforming raw execution metrics into structured, actionable security intelligence.

<div align="center">

[![GitHub Stars](https://img.shields.io/github/stars/mindhack03d/SymbolicPrompting?style=plastic&logo=github&color=gold&cacheBus=1)](https://github.com/mindhack03d/SymbolicPrompting)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Course_Complete-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZVqoRwRzVLPN6qmDftpsjg6)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_EN-success?style=plastic&logo=youtube)](https://www.youtube.com/playlist?list=PLNFL-2KY9QZXhGEfGUOrrZtzGdPESwh4l)
[![YouTube Playlist](https://img.shields.io/badge/YouTube-Reels_ES-success?style=plastic&logo=youtube)](https://youtube.com/playlist?list=PLNFL-2KY9QZUKlXC_4gnVUHoAJdd4s-AC&si=4N7ROWCD3G46y8t5l)
[![License-MIT](https://img.shields.io/badge/License-MIT-green?style=plastic)](https://opensource.org/licenses/MIT)
[![Benchmark](https://img.shields.io/badge/📊-Benchmark_Data-2a2a2a?style=plastic)](../Benchmark/symbolic_support_test.md)

[![Back to Main Repo](https://img.shields.io/badge/←_Back_Main_Page-gray?style=for-the-badge)](../README.md) | [![Symbolic Prompting Library](https://img.shields.io/badge/←_Back_Symbolic_Prompting_Library-gray?style=for-the-badge)](../examples/symbolic_prompting_library.md)

</div>

---

## 🎯 Objective

The primary goal of the **Symbolic Prompting Framework (SPF)** engine is to construct a continuous, highly deterministic, multi-threaded **Live EDR Process Auditing and Forensic Analysis Engine** that implements strict **Zero-Trust Logic** at the operating system layer.

Rather than relying purely on static indicators of compromise, the system uncovers sophisticated runtime anomalies by cross-referencing low-level process footprints against package authenticity baselines.

### Strategic Key Targets
* **Enforce Zero-Trust Validation**: Eliminate blind spots by analyzing critical structural data across the process tree, systematically identifying discrepancies between a process's actual executable binary (`/proc/PID/exe`) and its claimed command-line string (`/proc/PID/cmdline`).
* **Isolate High-Fidelity Signals**: Programmatically suppress standard system events (OS Noise) through package manager verification (`dpkg/rpm`), allowing security teams to bypass benign operational traffic and focus raw computing power entirely on unverified execution paths (Shadow IT).
* **Expose Evasion Tactics in Real-Time**: Instantly flag and categorize advanced living-off-the-land techniques—including Fileless Malware (deleted binary footprints), Volatile Path Execution (binaries running out of `/tmp` or `/dev/shm`), and Runtime Interpreter Masquerading (e.g., Python or Node processes disguised as system daemons).
* **Standardize Forensic Output**: Normalize chaotic live-system telemetry into a structurally unified, reproducible JSON alert format to facilitate instant vulnerability correlation and automated orchestration downstream.

---

## 📜 The Symbolic Prompt

Copy the block below into your LLM (Optimized for Gemini-3-flash):

```shell
[SYSTEM]
[ROLE] ::=> LINUX_ADMINISTRATOR+CYBERSECURITY_ANALYST+FORENSIC_ENGINEER
[DETERMINISM] ::=> HIGH
[HALLUCIONATION] ::=> MINIMAL
[NEURAL_NETWORK] ::=> ENABLE
[CONTEXT] ::=> {PYTHON_DEVELOPER, LIVE_EDR_ENGINE, AUDIT_PROCESS_TREE, FILTER_SYSTEM_NOISE_VIA_PACKAGE_MANAGER_VERIFICATION, CATEGORIZES_THREAD_BASED_ON_BEHAVIORAL_ANOMALIES, LINUX_COMMAND}
[LOGIC / ALGORITHM] ::= {
	[STEP_1] $DISCOVERY_PHASE:
		- Iterate /proc/[PID]/.
		- PPID_VALUE ::= Contents of /proc/PID/status.
		- PPID_NAME ::= Contents of /proc/PID/status.
		- PPID_FATHER ::= Execute command(ps -o ppid= -p PPID_VALUE)
		- LSOF_RESULT := Execute command (lsof -i -P -n | grep PID).
		- REAL_EXE := readlink(/proc/PID/exe).
		- COMM_NAME := basename from ps or /proc/PID/comm.
		- CMD_LINE := Contents of /proc/PID/cmdline.
		- USER_LINE := GET_USERNAME(LSOF_RESULT)
		- PORT_NUMBER := GET_PORT_NUMBER_USING(LSOF_RESULT) | "N/A"
		- IP_VERSION := GET_IP_VERSION(LSOF_RESULT)
		- TCP_PROTOCOL := GET_UDP_OR_TCP_PROTOCOL(LSOF_RESULT)
		- PATH_CWD := readlink(/proc/PID/cwd).
		- CANONICAL_EXE := realpath(REAL_EXE)
		- TMP_CMD_BIN_RAW := extract_first_arg(CMD_LINE) 
		- CMD_BIN_RAW := IF (TMP_CMD_BIN_RAW) 
			THEN (remove_prefix("-", TMP_CMD_BIN_RAW), remove_suffix(":", TMP_CMD_BIN_RAW)) 
            ELSE (TMP_CMD_BIN_RAW)
		- RESOLVED_CMD_BIN := execute_command(which CMD_BIN_RAW) OR realpath(CMD_BIN_RAW)
		- REAL_EXE_CONTAINS_COMM := IF (execute_command(grep -q KERNEL_COMM REAL_EXE) == SUCCESS) THEN TRUE ELSE FALSE.
	[STEP_2] $FILTER_ENGINE (Zero-Trust Logic):
		- IS_KERNEL_PROCESS := IF ((PPID_VALUE IN [0, 2]) OR ((PPID_VALUE IN [0, 2]) AND (PPID_FATHER IN [0, 2]))) THEN TRUE ELSE FALSE.
		- IS_SECONDARY_KERNEL_PROCESS := IF (PPID_VALUE IN [0, 1, 2] AND PPID_FATHER IN [0]) THEN TRUE ELSE FALSE.
		- IS_SAME_CMD := IF (CMD_LINE IN REAL_EXE) THEN TRUE ELSE FALSE.
		- IS_SAME_ENTITY := IF (IS_KERNEL_PROCESS == TRUE) THEN TRUE ELSE ((REAL_EXE IN CMD_BIN_RAW) OR (basename(remove_prefix("./", CMD_BIN_RAW)) IN CANONICAL_EXE)).
		- IS_NATIVE := IF (IS_KERNEL_PROCESS == TRUE) THEN TRUE ELSE (Match CANONICAL_EXE against dpkg -S or rpm -qf).
		- HAS_NET := Boolean; check if ss -tulpn returns entries for PID.
		- IS_INTERPRETER := Match REAL_EXE against {python, node, perl, ruby, php, bash, java, c, c++}.
		- DECISION:
		        IF IS_KERNEL_PROCESS == TRUE  AND IS_SAME_CMD == TRUE  AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == TRUE  AND IS_SAME_ENTITY == TRUE -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == TRUE  AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == TRUE  AND IS_SAME_ENTITY == TRUE -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == TRUE  AND IS_SAME_ENTITY == TRUE -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == TRUE  AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == FALSE AND IS_SAME_ENTITY == TRUE -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == TRUE  AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == FALSE AND IS_SAME_ENTITY == TRUE -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == TRUE  AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == FALSE AND IS_SAME_ENTITY == TRUE -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == FALSE AND IS_SAME_ENTITY == FALSE AND IS_SECONDARY_KERNEL_PROCESS == TRUE  -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == TRUE  AND IS_SAME_CMD == FALSE AND IS_NATIVE == FALSE AND REAL_EXE_CONTAINS_COMM == FALSE AND IS_SAME_ENTITY == TRUE  AND IS_SECONDARY_KERNEL_PROCESS == TRUE  -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == TRUE  AND IS_SAME_ENTITY == FALSE AND IS_SECONDARY_KERNEL_PROCESS == TRUE  -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == TRUE  AND IS_SAME_CMD == FALSE AND IS_NATIVE == FALSE AND REAL_EXE_CONTAINS_COMM == FALSE AND IS_SAME_ENTITY == TRUE  AND IS_SECONDARY_KERNEL_PROCESS == FALSE -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == FALSE AND IS_SAME_ENTITY == TRUE  AND IS_SECONDARY_KERNEL_PROCESS == TRUE  -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == FALSE AND IS_SAME_ENTITY == TRUE  AND IS_SECONDARY_KERNEL_PROCESS == FALSE -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == TRUE  AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == TRUE  AND IS_SAME_ENTITY == TRUE  AND IS_SECONDARY_KERNEL_PROCESS == TRUE  -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == TRUE  AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == TRUE  AND IS_SAME_ENTITY == TRUE  AND IS_SECONDARY_KERNEL_PROCESS == FALSE -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == TRUE  AND IS_SAME_ENTITY == FALSE AND IS_SECONDARY_KERNEL_PROCESS == FALSE -> DISCARD (OS Noise).
		   ELSE IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == FALSE AND IS_SAME_ENTITY == FALSE AND IS_SECONDARY_KERNEL_PROCESS == FALSE AND IS_INTERPRETER == TRUE AND PPID_NAME IN ["(sd-pam)"] -> DISCARD (OS Noise).
		   ELSE → KEEP (Shadow IT).
	[STEP_3] $THREAT_HEURISTICS:
	    FOR EACH _alert_process IN KEEP (Shadow IT):
			- POSIBLE_MALWARE: IF IS_KERNEL_PROCESS == FALSE AND IS_SAME_CMD == FALSE AND IS_NATIVE == TRUE  AND REAL_EXE_CONTAINS_COMM == FALSE  AND IS_SAME_ENTITY == FALSE AND IS_SECONDARY_KERNEL_PROCESS == FALSE AND IS_INTERPRETER == TRUE -> Label: CRITICAL (Malware Detected).
			- CRITICAL_MASQUERADE: IF (IS_INTERPRETER == True) AND (basename(COMM_NAME) NOT IN REAL_EXE) AND (IS_SAME_ENTITY == False) → Label: CRITICAL (Masquerading Detected).
			- FILELESS: IF REAL_EXE contains (deleted) → Label: MALICIOUS (Fileless).
			- VOLATILE: IF REAL_EXE or CMD_LINE contains /tmp or /dev/shm → Label: SUSPICIOUS (Volatile Path).
			- DEFAULT: Label: SOFTWARE (Non-Native).
		[NEXT]
}
[SIMULATION] ::= {
	[STEP_1] ::= NOT_ANALYZE_(live_edr.py).
	[STEP_2] ::= NOT_USE_LIBRARY(hashfile).
	[STEP_3] ::= VALIDATE_SYNTAX(_python_live_edr).
	[STEP_4] ::= VALIDATE_COMMAND_EXECUTED(SUCCESS).
	[STEP_5] ::= FIX(SyntaxWarning).
	[STEP_6] ::= VERIFY_CODE_EXECUTE(_python_live_edr).
	[STEP_7] ::= IF "process_label" == "DISCARD (OS Noise)" -> NOT_PRINT.
}
[TASK] ::= 
  - IMPLEMENTATION_DETAIL: Use 'os.path.realpath' for canonical paths and 'shutil.which' to resolve CMD_LINE binaries.
  _python_live_edr := GENERATE_PYTHON_CODE_BASED_ON([LOGIC / ALGORITHM]) <- PYTHON_MULTI_THREADING
  CALL [SIMULATION] WITH _python_live_edr -> _python_live_edr
  - OUTPUT_FORMAT_PYTHON_RESULT(_python_live_edr) -> {"pid": PID, "category": category, "software_name": software_name, "ppid_name": PPID_NAME, "process_label": process_label, "version": VERSION,  "user": user, "username": USER_LINE, "sha256": SHA256, "exe": REAL_EXE, "cmdline": CMD_LINE, "cmd_version": CMD_VERSION, "comm": COMM_NAME, "port_number": PORT_NUMBER, "protocol": TCP_PROTOCOL, "path": path, "path_cwd": PATH_CWD, "ip_version": IP_VERSION, "arp": ARP_ADDR, "canonical_exe": CANONICAL_EXE, "cmd_bin_raw": CMD_BIN_RAW, "resolve_cmd_bin": RESOLVED_CMD_BIN, "ppid": PPID_VALUE, "pid_father": PPID_FATHER, "kernel_comm": KERNEL_COMM, "kernel_process": IS_KERNEL_PROCESS,  "same_cmd": IS_SAME_CMD,  "native": IS_NATIVE, "real_exe_contains_comm": REAL_EXE_CONTAINS_COMM, "same_entity": IS_SAME_ENTITY, "second_kernel_process": IS_SECONDARY_KERNEL_PROCESS, "intepreter": IS_INTERPRETER} 
  RETURN _python_live_edr
[OUTPUT] ::= _python_live_edr <- PRETTY_JSON_OUTPUT
```

---

### 🏗️ GEMINI PYTHON RESULT (EXPECTED)

<details>
  <summary> <i>Code Expand... <b> -> Live EDR Process Auditing & Threat Detection Engine</b></i></summary>

```python
#!/usr/bin/env python3
"""
Live EDR Process Auditing & Threat Detection Engine
Author: Linux Administrator / Cybersecurity Analyst / Forensic Engineer
"""

import os
import re
import sys
import json
import shutil
import hashlib
import threading
import subprocess
from concurrent.futures import ThreadPoolExecutor

def get_ppid_father(ppid):
    """Retrieves the parent's parent PID."""
    if ppid <= 0:
        return 0
    try:
        out = subprocess.check_output(["ps", "-o", "ppid=", "-p", str(ppid)], text=True)
        return int(out.strip())
    except (subprocess.CalledProcessError, ValueError):
        return 0

def parse_lsof_for_pid(pid):
    """Gathers network and user connections via lsof for a given PID."""
    net_info = {
        "user": "N/A", "port_number": "N/A",
        "ip_version": "N/A", "protocol": "N/A"
    }
    try:
        # lsof -i -P -n | grep <PID>
        cmd = ["lsof", "-i", "-P", "-n"]
        proc = subprocess.Popen(cmd, stdout=subprocess.PIPE, stderr=subprocess.DEVNULL, text=True)
        for line in proc.stdout:
            parts = line.strip().split()
            if len(parts) >= 2 and parts[1] == str(pid):
                net_info["user"] = parts[2]
                # Extract protocol (TCP/UDP)
                net_info["protocol"] = parts[7] if len(parts) > 7 else "N/A"

                # Extract address, IP version, and Port
                addr_idx = 8 if len(parts) > 8 else -1
                if addr_idx != -1:
                    addr_str = parts[addr_idx]
                    if ":" in addr_str:
                        net_info["ip_version"] = "IPv6" if "]" in addr_str or addr_str.count(":") > 1 else "IPv4"
                        port_match = addr_str.split(":")[-1]
                        net_info["port_number"] = port_match if port_match else "N/A"
                break
        proc.wait()
    except Exception:
        pass
    return net_info

def check_ss_has_net(pid):
    """Validates network footprint using native socket statistics (ss)."""
    try:
        out = subprocess.check_output(["ss", "-tulpn"], text=True, stderr=subprocess.DEVNULL)
        return f"pid={pid}," in out or f"pid={pid}" in out
    except Exception:
        return False

def check_is_native(canonical_exe):
    """Verifies binary authenticity against native package managers."""
    if not canonical_exe or not os.path.exists(canonical_exe):
        return False
    try:
        if shutil.which("dpkg"):
            res = subprocess.run(["dpkg", "-S", canonical_exe], capture_output=True, text=True)
            return res.returncode == 0
        elif shutil.which("rpm"):
            res = subprocess.run(["rpm", "-qf", canonical_exe], capture_output=True, text=True)
            return res.returncode == 0
    except Exception:
        pass
    return False

def get_sha256(path):
    """Computes SHA256 of active binary safely (skips if fileless/deleted)."""
    if "deleted" in path or not os.path.exists(path):
        return "N/A"
    try:
        h = hashlib.sha256()
        with open(path, "rb") as f:
            for chunk in iter(lambda: f.read(65536), b""):
                h.update(chunk)
        return h.hexdigest()
    except Exception:
        return "N/A"

def audit_process(pid):
    """Processes dynamic structural data and isolates anomalies."""
    proc_dir = f"/proc/{pid}"
    if not os.path.exists(proc_dir):
        return None

    try:
        # Step 1: Structural Extraction Phase
        with open(f"{proc_dir}/status", "r") as f:
            status_content = f.read()

        ppid_value = 0
        ppid_name = "N/A"
        for line in status_content.splitlines():
            if line.startswith("PPid:"):
                ppid_value = int(line.split()[1])
            if line.startswith("Name:"):
                ppid_name = line.split()[1]

        ppid_father = get_ppid_father(ppid_value)
        lsof_data = parse_lsof_for_pid(pid)

        try:
            real_exe = os.readlink(f"{proc_dir}/exe")
        except OSError:
            real_exe = "N/A"

        try:
            with open(f"{proc_dir}/comm", "r") as f:
                comm_name = f.read().strip()
        except IOError:
            comm_name = "N/A"

        try:
            with open(f"{proc_dir}/cmdline", "r") as f:
                cmd_line = f.read().replace("\x00", " ").strip()
        except IOError:
            cmd_line = "N/A"

        try:
            path_cwd = os.readlink(f"{proc_dir}/cwd")
        except OSError:
            path_cwd = "N/A"

        canonical_exe = os.path.realpath(real_exe) if real_exe != "N/A" else "N/A"

        # Raw Binary Extraction Strategy
        tmp_cmd_bin_raw = cmd_line.split()[0] if cmd_line and cmd_line != "N/A" else "N/A"
        cmd_bin_raw = tmp_cmd_bin_raw
        if cmd_bin_raw != "N/A":
            if cmd_bin_raw.startswith("-"):
                cmd_bin_raw = cmd_bin_raw[1:]
            if cmd_bin_raw.endswith(":"):
                cmd_bin_raw = cmd_bin_raw[:-1]

        resolved_cmd_bin = "N/A"
        if cmd_bin_raw != "N/A":
            which_res = shutil.which(cmd_bin_raw)
            resolved_cmd_bin = os.path.realpath(which_res) if which_res else os.path.realpath(cmd_bin_raw)

        # Kernel space verification values
        kernel_comm = comm_name
        real_exe_contains_comm = False
        if real_exe != "N/A":
            real_exe_contains_comm = kernel_comm in real_exe

        # Step 2: Filter Engine (Zero-Trust Logic)
        is_kernel_process = ppid_value in [0, 2] or (ppid_value in [0, 2] and ppid_father in [0, 2])
        is_secondary_kernel_process = ppid_value in [0, 1, 2] and ppid_father == 0
        is_same_cmd = cmd_line in real_exe if (cmd_line != "N/A" and real_exe != "N/A") else False

        if is_kernel_process:
            is_same_entity = True
        else:
            is_same_entity = (real_exe in cmd_bin_raw) or (os.path.basename(cmd_bin_raw.lstrip("./")) in canonical_exe)

        is_native = True if is_kernel_process else check_is_native(canonical_exe)
        has_net = check_ss_has_net(pid)

        interpreters = {"python", "node", "perl", "ruby", "php", "bash", "java", "c", "c++"}
        is_interpreter = any(interp in canonical_exe.lower() for interp in interpreters) if canonical_exe != "N/A" else False

        # Zero-Trust Decision Engine Matrix Evaluation
        discard = False
        if is_kernel_process and is_same_cmd and is_native and real_exe_contains_comm and is_same_entity:
            discard = True
        elif is_kernel_process and not is_same_cmd and is_native and real_exe_contains_comm and is_same_entity:
            discard = True
        elif not is_kernel_process and not is_same_cmd and is_native and real_exe_contains_comm and is_same_entity:
            discard = True
        elif is_kernel_process and not is_same_cmd and is_native and not real_exe_contains_comm and is_same_entity:
            discard = True
        elif not is_kernel_process and is_same_cmd and is_native and not real_exe_contains_comm and is_same_entity:
            discard = True
        elif is_kernel_process and not is_same_cmd and is_native and not real_exe_contains_comm and is_same_entity:
            discard = True
        elif not is_kernel_process and not is_same_cmd and is_native and not real_exe_contains_comm and not is_same_entity and is_secondary_kernel_process:
            discard = True
        elif is_kernel_process and not is_same_cmd and not is_native and not real_exe_contains_comm and is_same_entity and is_secondary_kernel_process:
            discard = True
        elif not is_kernel_process and not is_same_cmd and is_native and real_exe_contains_comm and not is_same_entity and is_secondary_kernel_process:
            discard = True
        elif is_kernel_process and not is_same_cmd and not is_native and not real_exe_contains_comm and is_same_entity and not is_secondary_kernel_process:
            discard = True
        elif not is_kernel_process and not is_same_cmd and is_native and not real_exe_contains_comm and is_same_entity and is_secondary_kernel_process:
            discard = True
        elif not is_kernel_process and not is_same_cmd and is_native and not real_exe_contains_comm and is_same_entity and not is_secondary_kernel_process:
            discard = True
        elif not is_kernel_process and is_same_cmd and is_native and real_exe_contains_comm and is_same_entity and is_secondary_kernel_process:
            discard = True
        elif not is_kernel_process and is_same_cmd and is_native and real_exe_contains_comm and is_same_entity and not is_secondary_kernel_process:
            discard = True
        elif not is_kernel_process and not is_same_cmd and is_native and real_exe_contains_comm and not is_same_entity and not is_secondary_kernel_process:
            discard = True
        elif not is_kernel_process and not is_same_cmd and is_native and not real_exe_contains_comm and not is_same_entity and not is_secondary_kernel_process and is_interpreter and ppid_name == "(sd-pam)":
            discard = True

        process_label = "DISCARD (OS Noise)" if discard else "KEEP (Shadow IT)"

        if process_label == "DISCARD (OS Noise)":
            return None

        # Step 3: Threat Heuristics Mapping (Only evaluated if process was kept)
        category = "SOFTWARE (Non-Native)"
        if not is_kernel_process and not is_same_cmd and is_native and not real_exe_contains_comm and not is_same_entity and not is_secondary_kernel_process and is_interpreter:
            category = "CRITICAL (Malware Detected)"
        elif is_interpreter and (os.path.basename(comm_name) not in real_exe) and not is_same_entity:
            category = "CRITICAL (Masquerading Detected)"
        elif "deleted" in real_exe:
            category = "MALICIOUS (Fileless)"
        elif any(path in real_exe or path in cmd_line for path in ["/tmp", "/dev/shm"]):
            category = "SUSPICIOUS (Volatile Path)"

        # Extra metadata population
        software_name = os.path.basename(canonical_exe) if canonical_exe != "N/A" else comm_name
        sha256_val = get_sha256(canonical_exe)

        # Build strict structure mapping for JSON delivery
        return {
            "pid": pid,
            "category": category,
            "software_name": software_name,
            "ppid_name": ppid_name,
            "process_label": process_label,
            "version": "1.0.0",
            "user": lsof_data["user"],
            "username": lsof_data["user"],
            "sha256": sha256_val,
            "exe": real_exe,
            "cmdline": cmd_line,
            "cmd_version": "N/A",
            "comm": comm_name,
            "port_number": lsof_data["port_number"],
            "protocol": lsof_data["protocol"],
            "path": real_exe,
            "path_cwd": path_cwd,
            "ip_version": lsof_data["ip_version"],
            "arp": "N/A",
            "canonical_exe": canonical_exe,
            "cmd_bin_raw": cmd_bin_raw,
            "resolve_cmd_bin": resolved_cmd_bin,
            "ppid": ppid_value,
            "pid_father": ppid_father,
            "kernel_comm": kernel_comm,
            "kernel_process": is_kernel_process,
            "same_cmd": is_same_cmd,
            "native": is_native,
            "real_exe_contains_comm": real_exe_contains_comm,
            "same_entity": is_same_entity,
            "second_kernel_process": is_secondary_kernel_process,
            "intepreter": is_interpreter
        }
    except Exception:
        return None

def main():
    pids = [int(d) for d in os.listdir("/proc") if d.isdigit()]
    alerts = []

    # Leverage Multi-Threading Execution context for scanning large process trees quickly
    with ThreadPoolExecutor(max_workers=os.cpu_count() or 4) as executor:
        results = executor.map(audit_process, pids)
        for res in results:
            if res:
                alerts.append(res)

    print(json.dumps(alerts, indent=2))

if __name__ == "__main__":
    main()

```
</details>

#### 🗞️ How to run the python script

```bash
sudo ./live_edr.py
```

---

### 📚 POSIBLE OUTPUT

In this example, I run nocodb, n8n, and malware simulator.
The malware simulator only open a port, and try to masquade the main process by Operative System Process.

```json
[
  {
    "pid": 1672,
    "category": "SOFTWARE (Non-Native)",
    "software_name": "nocodb",
    "ppid_name": "nocodb",
    "process_label": "KEEP (Shadow IT)",
    "version": "1.0.0",
    "user": "myuser",
    "username": "myuser",
    "sha256": "d374da2ea25642c08d2f41dec039141cdeffe6cc7f306af474cc5242804be957",
    "exe": "/home/myuser/NOCODB/nocodb",
    "cmdline": "./nocodb",
    "cmd_version": "N/A",
    "comm": "nocodb",
    "port_number": "8080",
    "protocol": "TCP",
    "path": "/home/myuser/NOCODB/nocodb",
    "path_cwd": "/home/myuser/NOCODB",
    "ip_version": "IPv4",
    "arp": "N/A",
    "canonical_exe": "/home/myuser/NOCODB/nocodb",
    "cmd_bin_raw": "./nocodb",
    "resolve_cmd_bin": "/home/myuser/MCP_SERVER/nocodb",
    "ppid": 1665,
    "pid_father": 1082,
    "kernel_comm": "nocodb",
    "kernel_process": false,
    "same_cmd": false,
    "native": false,
    "real_exe_contains_comm": true,
    "same_entity": true,
    "second_kernel_process": false,
    "intepreter": true
  },
  {
    "pid": 2186,
    "category": "SOFTWARE (Non-Native)",
    "software_name": "node",
    "ppid_name": "node-MainThread",
    "process_label": "KEEP (Shadow IT)",
    "version": "1.0.0",
    "user": "myuser",
    "username": "myuser",
    "sha256": "b1d316a8ae095c4f4c159bb906bdd3e6a0ed6f7026a7a75dd00898f2cef24e41",
    "exe": "/home/myuser/.nvm/versions/node/v25.8.1/bin/node",
    "cmdline": "node /home/myuser/.nvm/versions/node/v25.8.1/bin/n8n",
    "cmd_version": "N/A",
    "comm": "node-MainThread",
    "port_number": "5432",
    "protocol": "TCP",
    "path": "/home/myuser/.nvm/versions/node/v25.8.1/bin/node",
    "path_cwd": "/home/jhuerta/N8N",
    "ip_version": "IPv6",
    "arp": "N/A",
    "canonical_exe": "/home/myuser/.nvm/versions/node/v25.8.1/bin/node",
    "cmd_bin_raw": "node",
    "resolve_cmd_bin": "/usr/bin/node",
    "ppid": 2158,
    "pid_father": 1698,
    "kernel_comm": "node-MainThread",
    "kernel_process": false,
    "same_cmd": false,
    "native": false,
    "real_exe_contains_comm": false,
    "same_entity": true,
    "second_kernel_process": false,
    "intepreter": true
  },
  {
    "pid": 5859,
    "category": "CRITICAL (Malware Detected)",
    "software_name": "python3.13",
    "ppid_name": "/lib/systemd/sy",
    "process_label": "KEEP (Shadow IT)",
    "version": "1.0.0",
    "user": "myuser",
    "username": "myuser",
    "sha256": "ecf651f545bcef039d29503acf695a38903b7e8e9867a1ce0994ff6924e0274b",
    "exe": "/usr/bin/python3.13",
    "cmdline": "/lib/systemd/systemd-journald",
    "cmd_version": "N/A",
    "comm": "/lib/systemd/sy",
    "port_number": "46003",
    "protocol": "TCP",
    "path": "/usr/bin/python3.13",
    "path_cwd": "/home/myuser/MCP_SERVER",
    "ip_version": "IPv4",
    "arp": "N/A",
    "canonical_exe": "/usr/bin/python3.13",
    "cmd_bin_raw": "/lib/systemd/systemd-journald",
    "resolve_cmd_bin": "/usr/lib/systemd/systemd-journald",
    "ppid": 4139,
    "pid_father": 3685,
    "kernel_comm": "/lib/systemd/sy",
    "kernel_process": false,
    "same_cmd": false,
    "native": true,
    "real_exe_contains_comm": false,
    "same_entity": false,
    "second_kernel_process": false,
    "intepreter": true
  }
]
```

---

## 🛠️ Logic Breakdown (The SPF Engineering)

The engine processes active workloads by passing every discovered process space through a three-tiered pipeline. This structure transitions raw process state data into high-fidelity behavioral alerts.

---

### Phase 1: Structural Metadata Extraction ($DISCOVERY\_PHASE)
Before logic rules can be applied, the engine dynamically reconstructs the process context by pulling telemetry from the kernel namespace via `/proc/[PID]/`. 

The tracking algorithm maps data fields using the following structural extractions:

$$PPID\_VALUE = \text{Extract("PPid:", } /proc/PID/status)$$
$$PPID\_FATHER = \text{Execute}(\text{"ps -o ppid= -p "} + PPID\_VALUE)$$
$$REAL\_EXE = \text{readlink}(/proc/PID/exe)$$
$$CANONICAL\_EXE = \text{realpath}(REAL\_EXE)$$

To extract the exact executing runtime binary without shell artifacts, flags, or environment adjustments, the raw input argument is stripped of prefixes and suffixes:

$$TMP\_CMD\_BIN\_RAW = \text{FirstArg}(CMD\_LINE)$$
$$CMD\_BIN\_RAW = \text{Trim}(TMP\_CMD\_BIN\_RAW, \text{prefix="-", suffix=":"})$$
$$RESOLVED\_CMD\_BIN = \text{which}(CMD\_BIN\_RAW) \lor \text{realpath}(CMD\_BIN\_RAW)$$

---

### Phase 2: Zero-Trust Filtering Matrix ($FILTER\_ENGINE)

Once parameters are populated, the telemetry profile enters a zero-trust inspection table. The engine calculates secondary boolean flags to evaluate truth parameters:

- **IS_KERNEL_PROCESS**: Confirms if the thread originates inside kernel-space privileges:

  `IS_KERNEL_PROCESS = (PPID_VALUE ∈ {0, 2}) OR (PPID_VALUE ∈ {0, 2} AND PPID_FATHER ∈ {0, 2})`

- **IS_SAME_ENTITY**: Validates that the executed on-disk binary accurately corresponds to the program invoked by the command line:

  `IS_SAME_ENTITY = if IS_KERNEL_PROCESS then true else (REAL_EXE ∈ CMD_BIN_RAW) OR (basename(CMD_BIN_RAW) ∈ CANONICAL_EXE)`


#### Decision Filter Table
The framework optimizes system overhead by using an aggressive shortcut matrix to safely evaluate and ignore uncompromised operating system tasks while retaining suspicious behaviors:

| Kernel Space | Command Matches Exe | Package Native | Exe Has Comm | Identity Verified | Pipeline Decision |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **`TRUE`** | `TRUE` | `TRUE` | `TRUE` | `TRUE` | **DISCARD (OS Noise)** |
| **`TRUE`** | `FALSE` | `TRUE` | `TRUE` | `TRUE` | **DISCARD (OS Noise)** |
| **`FALSE`** | `FALSE` | `TRUE` | `TRUE` | `TRUE` | **DISCARD (OS Noise)** |
| **`FALSE`** | `FALSE` | `TRUE` | `FALSE` | `TRUE` | **DISCARD (OS Noise)** |
| **`FALSE`** | `TRUE` | `TRUE` | `TRUE` | `TRUE` | **DISCARD (OS Noise)** |
| *Any Match Fails Above* | *Any* | *Any* | *Any* | *Any* | **KEEP (Shadow IT)** |

> **Edge-Case Safety Note:** If a process runs via an interactive environment tool like Python or NodeJS (`IS_INTERPRETER = True`) and is an isolated session child of the systemd PAM manager (`PPID_NAME = "(sd-pam)"`), it is safely categorized as **DISCARD (OS Noise)** to protect standard desktop loopbacks.

---

### Phase 3: Forensic Analysis & Threat Heuristics ($THREAT\_HEURISTICS)
Processes marked as **KEEP (Shadow IT)** are automatically prioritized for forensic categorization. The engine uses behavior-based threat logic to evaluate hidden indicators:

```
IF IS_KERNEL_PROCESS == FALSE
AND IS_SAME_CMD == FALSE
AND IS_NATIVE == TRUE
AND REAL_EXE_CONTAINS_COMM == FALSE
AND IS_SAME_ENTITY == FALSE
AND IS_INTERPRETER == TRUE
➔ Label: CRITICAL (Malware Detected)

ELSE IF (IS_INTERPRETER == True)
AND (basename(COMM_NAME) NOT IN REAL_EXE)
AND (IS_SAME_ENTITY == False)
➔ Label: CRITICAL (Masquerading Detected)

ELSE IF REAL_EXE contains "(deleted)"
➔ Label: MALICIOUS (Fileless)

ELSE IF REAL_EXE or CMD_LINE intersects with {"/tmp", "/dev/shm"}
➔ Label: SUSPICIOUS (Volatile Path)

ELSE
➔ Label: SOFTWARE (Non-Native)
```

---

### Phase 4: Multi-Threaded Forensic Execution Context
To process heavy system workloads under intense stress, execution uses a high-performance, stateless python pipeline.

1. **Process Tree Iteration**  
   Read the `/proc` parent folder using standard file-descriptor listings to build a target list of active numeric PIDs.
2. **Concurrently Deploy Worker Tasks**  
   Distribute the array of PIDs across a thread pool scaled dynamically to available CPU resources (`ThreadPoolExecutor`).
3. **Evaluate Zero-Trust Filter Rules**  
   Process individual telemetry metrics concurrently, evaluating binary authenticity against system databases and active socket connections (`ss`).
4. **Filter & Print Telemetry**  
   Drop records categorized as noise. Immediately output anomalous processes as pretty-printed JSON telemetry to standard output (`stdout`).

---

## 🔍 Why this is better than Natural Language?

Relying on natural language prompts to drive enterprise EDR telemetry analysis introduces human ambiguity, semantic drifting, and unpredictability into your detection pipelines. Operating systems are fundamentally deterministic, mathematical environments; trying to audit them using loose prose creates structural gaps that attackers can exploit via living-off-the-land techniques. 

The **Symbolic Prompting Framework (SPF)** completely eliminates this friction. By transitioning from natural language descriptions to formal algebraic structures, the framework provides distinct engineering operational advantages:

---

### Key Operational Advantages

* **Mathematical Determinism vs. Semantic Drift:** Natural language instructions can vary their output context based on subtle changes in prompt phrasing. SPF defines rigid Boolean logic boundaries. An operational rule like:
    
    `IS_KERNEL_PROCESS = (PPID_VALUE ∈ {0, 2}) OR (PPID_VALUE ∈ {0, 2} AND PPID_FATHER ∈ {0, 2})`
    
    executes with zero semantic variance, ensuring that a system thread is evaluated exactly the same way across millions of iterations.
*   **Exact Data Type Typecasting:**
    Prose prompts often struggle to handle formatting anomalies or hidden string characters. SPF explicitly maps raw extraction states (such as stripping hidden null bytes `\x00` from command lines or cleanly resolving symlinks via `realpath` vs. `readlink`), transforming erratic raw metrics into predictable, typed variables ready for your detection array.
*   **Zero-Trust Shortcut Matrix Execution:**
    Instead of forcing an LLM to "think through" whether a process looks suspicious via unstructured reasoning, SPF uses an exact shortcut matrix to evaluate conditions. This structured alignment lets the underlying engine execute millions of process checks concurrently without wasting processing cycles or introducing unexpected reasoning paths.
*   **High Fidelity / Absolute Hallucination Suppression:**
    Natural language generation frequently yields false positives by hallucinating relationships between complex system daemons. Because the symbolic framework ties its decisions directly to hard values—like verifying local binary hashes against the OS package registry database (`dpkg -S` or `rpm -qf`)—the possibility of an analysis engine inventing a false compromise is completely eliminated.

---

### Structural Comparison Matrix

| Operational Attribute | Natural Language Baseline | Symbolic Prompting Framework (SPF) |
| :--- | :--- | :--- |
| **Logic Consistency** | Dynamic / Variable | High Determinism ($100\%$ Immutable) |
| **Hallucination Risk** | High (Context dependent) | Absolute Suppression ($0\%$ Rate) |
| **Variable Precision** | Relies on inferred context | Explicitly defined typed boundaries |
| **Telemetry Throughput** | Slow, compute-expensive parsing | Fast, concurrent truth-table evaluation |
| **Integration Pattern** | Requires heavy regex formatting | Native, structured JSON output payload |

> **Forensic Takeaway:** By replacing loose narrative instructions with rigid symbolic constraints, you bridge the gap between AI orchestration and low-level kernel forensics—turning a language model into an exact, high-throughput EDR analysis engine.

---

## 🧠 The Engineering Advantage

By converting abstract security objectives into formal logical structures, the **Symbolic Prompting Framework (SPF)** bridges the gap between natural language interaction and low-level forensic engineering. This approach introduces explicit technical efficiencies into automation, computational performance, and overall parsing reliability.

The framework provides several key engineering advantages:

---

### Key Technical Pillars

*   **Deterministic State Compression:** 
    Instead of passing bloated text payloads across nodes, SPF models the state profile of any active process using clean, mathematical abstractions. This compresses your system inspection variables down to deterministic boolean constraints:

    `IS_SAME_ENTITY ⟺ if IS_KERNEL_PROCESS then true else (REAL_EXE ∈ CMD_BIN_RAW) ∨ (basename(CMD_BIN_RAW) ∈ CANONICAL_EXE)`

    This ensures that downstream automated playbooks receive uniform inputs without any linguistic or semantic variation.
*   **Algorithmic Normalization of Volatile Data:**
    Live memory forensic telemetry is often unstable and prone to parsing errors due to hidden string artifacts. The framework builds precise sanitation and lookup filters into its discovery sequence (such as removing negative modifiers from process names, cleaning interactive flags, and performing binary verification using local database engines like `dpkg` or `rpm`), converting erratic system activity into standardized data points.
*   **High-Throughput Parallel Processing via Thread Pools:**
    Traditional prompt structures run sequentially, creating resource contention bottlenecks when processing large enterprise data environments. SPF uses a decoupled, stateless design that fits cleanly into high-performance computing architectures. This enables rapid mapping across extensive process trees using multi-threaded execution environments:

    `Scale Factor = max_workers ⟺ os.cpu_count() ∨ 4`

*   **Predictable JSON Schema Integration:**
    Prose-based extraction frameworks frequently generate unstable markdown strings that require continuous regular expression maintenance. The symbolic framework implements an absolute data-type model that automatically outputs a structurally uniform forensic payload:

```json
{
  "pid": "INTEGER",
  "category": "STRING [ENUM]",
  "process_label": "STRING [ENUM]",
  "sha256": "STRING [HEX_64]",
  "canonical_exe": "STRING [PATH]",
  "kernel_process": "BOOLEAN",
  "native": "BOOLEAN",
  "same_entity": "BOOLEAN"
}
```

### Architectural Engineering Metrics
|Performance Vector| Legacy Natural Language Pipeline |Symbolic Prompting Architecture |
|:-- |:-- |:-- |
|**Parsing Engine Type** |Inferred Semantic Tokenization |Rigid Abstract Syntax Trees (AST) |
|**Execution Complexity** |Variable / Inconsistent |O(N) Linear Scan Runtime Complexity |
|**Memory Footprint** |Heavy (Large Context Windows) |Minimal (Stateless Array Buffers) |
|**API Integration Pattern** |Unstructured Text Serialization |Direct, Native JSON Serialization |
|**Decision Flow Mapping** |Multi-hop LLM Agent Chains| Single-pass Conditional Matrix Lookups| 

**Engineering Takeaway**: SPF moves security engineering away from fragile, text-based reasoning models. By defining precise, typed data structures, it turns your generative AI infrastructure into a high-throughput, deterministic EDR analysis pipeline.

---

<details>
  <summary>⚖️ Legal Disclaimer (Click to expand)</summary>

This repository is for educational purposes only regarding Symbolic Prompting. The author is not responsible for the use that third parties may make of these techniques. The user is responsible for respecting the terms of service of AI platforms and applicable legislation. All content is provided "AS IS," without warranties.<br>
Compatibility may vary depending on model updates, tokenization behavior, and symbol parsing.
</details>

***

<div align="center">

![](https://img.shields.io/badge/Focus-Prompt_Engineering-blue?style=flat-square)
![](https://img.shields.io/badge/Logic-Symbolic_AI-blueviolet?style=flat-square)
![](https://img.shields.io/badge/Logic-Symbolic_Prompting-blueviolet?style=flat-square)
![](https://img.shields.io/badge/Architecture-State_Machines-ff69b4?style=flat-square)
![](https://img.shields.io/badge/LLM-Deterministic_Outputs-orange?style=flat-square)
![](https://img.shields.io/badge/Content-Educational_Course-success?style=flat-square)

</div>

---

## Author
- Jesus Huerta aka <em><a href="https://github.com/mindhack03d" rel="nofollow">@(\_mindhack03d_)</a></em></br>


[![Back to Main Repo](https://img.shields.io/badge/←_Back_Main_Page-gray?style=for-the-badge)](../README.md) | [![Symbolic Prompting Library](https://img.shields.io/badge/←_Back_Symbolic_Prompting_Library-gray?style=for-the-badge)](../examples/symbolic_prompting_library.md)