# Mixamo Auto Control Rig v1.6.0 — Python 3 Compatibility Patch

An unofficial Python 3 compatibility patch for **Mixamo Auto Control Rig v1.6.0**, designed to help the legacy tool run in newer versions of Autodesk Maya.

The original Mixamo Auto Control Rig was developed for Python 2, which is no longer supported by modern versions of Maya.

This project updates the legacy Python code for compatibility with Python 3 without distributing the original rigging tool.

## Compatibility

| Software | Status |
|---|---|
| Autodesk Maya 2024 | Tested — UI launches and character rigging tested |
| Autodesk Maya 2026 | Not fully tested |
| Python 3 | Supported by the compatibility changes |

**Note:** This is an experimental compatibility patch. Some features may still require additional fixes.

## Requirements

- Original Mixamo Auto Control Rig v1.6.0 package
- Autodesk Maya 2024 or 2026
- Git installed on your computer

You must obtain the original Mixamo Auto Control Rig package separately.

## Installation

### Step 1 — Download the original tool

Obtain and extract the original **Mixamo Auto Control Rig v1.6.0** package.

The extracted package should contain the `MayaAutoControlRig` folder.

### Step 2 — Download the Python 3 patch

Download the following file from this repository:

`Mixamo_Auto_Control_Rig_v1.6.0_Python3.patch`

Place it inside the extracted original package's root folder, alongside `MayaAutoControlRig`.

### Step 3 — Apply the patch

Open a terminal in the extracted package's root folder.

First, check whether the patch can be applied:

```bash
git apply --unidiff-zero --check Mixamo_Auto_Control_Rig_v1.6.0_Python3.patch
```

If no errors appear, apply the patch:

```bash
git apply --unidiff-zero Mixamo_Auto_Control_Rig_v1.6.0_Python3.patch
```

**Important:** Apply this patch to a clean, unmodified copy of the original v1.6.0 package. Do not apply it to an already patched installation.

### Step 4 — Install in Maya

Copy the patched `MayaAutoControlRig` folder into your Maya scripts directory.

For Maya 2024:

```text
Documents/maya/2024/scripts/
```

For Maya 2026:

```text
Documents/maya/2026/scripts/
```

If an existing installation is present, back it up before replacing it.

Restart Maya after copying the files.

### Step 5 — Launch the tool

Use the original Mixamo Auto Control Rig launcher, or open Maya's Script Editor, switch to Python, and execute:

```python
from MayaAutoControlRig.UI.Main_UI import MIXAMO_AutoControlRig_UI

ui = MIXAMO_AutoControlRig_UI()
```

## What's Changed?

The compatibility patch includes:

- Conversion of legacy Python 2 syntax to Python 3.
- Updated Python module imports and relative import paths.
- Replacement of deprecated Python functions and modules.
- Compatibility adjustments for newer Maya Python environments.

The patch modifies 13 Python files from the original package.

## Testing

**Maya 2024:** The patch was successfully applied, the plugin imported, the user interface launched, and character rigging was tested.

**Maya 2026:** Full functionality has not yet been verified.

Feedback and bug reports are welcome through GitHub Issues.

## Future Plans

A standalone Windows patcher is being explored to simplify installation without requiring users to run Git commands.

This is not included in the current release.

## Credits

**Original Mixamo Auto Control Rig:** Dan Babcock / Mixamo

**Python 3 compatibility modifications:** RazifHaque

All credit for the original rigging system remains with its respective creators.

## Disclaimer

This is an unofficial, community-maintained compatibility project and is not affiliated with or endorsed by Adobe, Mixamo, or Autodesk.

This repository provides a patch rather than the complete original Mixamo Auto Control Rig package. Users must obtain the original software separately and comply with its applicable terms.

The patch is provided as-is, without warranty or guaranteed compatibility.
