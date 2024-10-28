

# Backdoor scanner by Fezco

![Project Banner](https://via.placeholder.com/728x90.png?text=Lua+Script+Scanner)

A C++ console application designed to scan Lua scripts for potential backdoors, suspicious links, and obfuscated code. This tool is particularly useful for FiveM developers who want to ensure their Lua scripts are free from malicious code.

---

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
  - [How It Works](#how-it-works)
- [Example Output](#example-output)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Features

- **Backdoor Detection**: Scans for suspicious functions and patterns often used in backdoors.
- **Link Scanning**: Identifies links within scripts, excluding known safe links like `discord.gg` or `discord.webhook`.
- **Obfuscation Detection**: Flags obfuscated or encoded code that may be hiding malicious functionality.
- **Detailed Logging**: Outputs detailed logs of findings, including file paths, line numbers, and specific issues found.
- **Cleaning Option**: Option to automatically clean scripts by removing detected malicious code.

## Installation

1. **Download the compiled release**:
  [Download latest release](https://fezco.nl)


## Usage

1. **Prepare folders**:
   Ensure the `scripts` folder contains the Lua scripts you wish to scan. This folder should be in the same directory as the compiled application.

2. **Run the application**:
   ```bash
   ./lua_script_scanner
   ```

3. **Choose an option**:
   - **Option 1**: Scans scripts for backdoors, suspicious links, and obfuscation, logging findings to the `output` folder.
   - **Option 2**: Scans and removes detected issues, saving cleaned files to the `fixed` folder and generating detailed logs of modifications.

---

## How It Works

### Step-by-Step Overview

1. **Run the Application**  
   Start by running the compiled program

2. **Choose a Scanning Option**
   - **Option 1**: Scans all Lua scripts in the `scripts` folder and logs suspicious findings to the `output` folder without altering files.
   - **Option 2**: Scans and removes detected malicious code from Lua scripts in the `scripts` folder, saves cleaned versions in the `fixed` folder, and logs changes made.


4. **Detection and Logging**  
   - The scanner searches each line of code in each Lua file for:
     - **Suspicious URLs** (excluding common safe links like `discord.gg` or `discord.com/api/webhooks/)`)
     - **Backdoor Patterns** (e.g., `loadstring`, `RunCode`, `decode`)
     - **Obfuscated Code** or other potentially malicious functions.
   - When suspicious code is found:
     - **Option 1**: Logs file path, line number, specific code flagged, and reason for flagging in a log file saved in the `output` folder.
     - **Option 2**: Removes flagged code from the file, saves the cleaned version in the `fixed` folder, and logs the details of every removal.

5. **Review Logs and Results**
   - After scanning, review the `output` or `fixed` folders:
     - **Option 1 Logs**: Provides a full report of flagged code in `output`, but does not alter original scripts.
     - **Option 2 Logs and Cleaned Files**: Saved in `fixed`, these logs document changes made to each file.

---

## Example Output

Here’s what you might see after running the application with **Option 1** or **Option 2**:

### Console Output
```plaintext
██   ██ ██  ██████  ██   ██     ██      ███████  █████  ██   ██ ███████ 
██   ██ ██ ██       ██   ██     ██      ██      ██   ██ ██  ██  ██      
███████ ██ ██   ███ ███████     ██      █████   ███████ █████   ███████ 
██   ██ ██ ██    ██ ██   ██     ██      ██      ██   ██ ██  ██       ██ 
██   ██ ██  ██████  ██   ██     ███████ ███████ ██   ██ ██   ██ ███████ 

                         Made by FezcoSmokes

Progress: 
[#############################               ] 60%
```

### Detailed Log Example (in `output` or `fixed`)
```plaintext
Filename: myScript.lua
Line 45: loadstring("encoded_string") (Reason: Obfuscated code detected)
Line 78: https://unknownsite.com/link (Reason: Suspicious URL detected)
```

Each log entry includes:
- **Filename**: The Lua file scanned.
- **Line Number**: The line where the issue was found.
- **Code Snippet**: The specific code flagged.
- **Reason**: Why it was flagged (e.g., "Obfuscated code detected").

---

## FAQ

### Why does my antivirus flag this as a trojan?

Due to certain scanning and file-modifying functions, antivirus software might flag this application as a potential threat. This is a false positive. To avoid this, we recommend:

1. Running the application in a safe environment.
2. Reviewing the code to ensure it aligns with your security standards.


---

## Contributing

Contributions are welcome! Feel free to submit pull requests to improve detection, add new features, or resolve issues.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

---

## Contact

For questions, reach out to the creator:

- **Website**: [fezco.nl](https://fezco.nl)
- **Highleaks Profile**: [Highleaks](https://highleaks.com)

---

Made by **FezcoSmokes**
