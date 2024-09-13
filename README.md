# GodotJS-Dependencies
Workflows to build all dependencies of GodotJS (v8 and libwebsockets).


- https://github.com/actions/runner-images
- https://github.com/actions/checkout
- https://github.com/actions/create-release


## Windows Toolset

Different Visual C++ Compilers are involved in different prebuilt GodotJS dependency releases:

| Package | Workflow Runners | Libraries | Toolset | Platforms/Architectures |
|---|---|---|---|---|
|[v8_r7](https://github.com/ialex32x/GodotJS-Dependencies/releases/download/v8_r7/v8_r7.zip)| windows-latest(2022)<br/>ubuntu-latest(22.04) |v8(12.4.254.20)| MSVC v143(14.40.33807)| Windows(x86_64)<br/>Linux(x86_64)<br/>MacOS(ARM64) |
|[v8_r9](https://github.com/ialex32x/GodotJS-Dependencies/releases/download/v8_r9/v8_r9.zip)| windows-latest(2022)<br/>ubuntu-latest(22.04) |v8(12.4.254.20)| VS2022(17.11.3)<br/> MSVC v143(14.41.34120)| Windows(x86_64)<br/>Linux(x86_64)<br/>MacOS(ARM64)<br/>Android(ARM64-v8a)<br/>iOS(ARM64) |
|[v8_r10](https://github.com/ialex32x/GodotJS-Dependencies/releases/download/v8_r10/v8_r10.zip)| windows-2019<br/>ubuntu-22.04 |v8(12.4.254.21)| MSVC v142(14.29.30133) | Windows(x86_64)<br/>Linux(x86_64)<br/>MacOS(ARM64)<br/>Android(ARM64-v8a)<br/>iOS(ARM64) |

> [!NOTE]
> Install specific VS 2022 MSVC toolset for different pacakge you used to avoid linkage errors.

-----

Why **windows_x86_64_release** does not follow the same naming rules?
> godot 4.3.1 generates `ActiveProjectItemList_` variable name with the path name (see methods.py)
> it'll fail if the path contains '.' or any other characters invalid as variable name
> detect and rename them for better compatibility
