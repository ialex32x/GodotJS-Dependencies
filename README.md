# GodotJS-Dependencies
Workflows to build all dependencies of GodotJS (v8 and libwebsockets).


- https://github.com/actions/runner-images
- https://github.com/actions/checkout
- https://github.com/actions/create-release


## Windows Toolchain

This workflow uses `windows-latest` runner to build v8 for Windows. 
Different Visual C++ Compilers are involved in different prebuilt GodotJS dependency releases:

| Package | Libraries | MSVC | Platforms/Architectures |
|---|---|---|---|
|[v8_r7](https://github.com/ialex32x/GodotJS-Dependencies/releases/download/v8_r7/v8_r7.zip)|v8(12.4.254.20)| v143(14.40.33807)| Windows(x86_64), Linux(x86_64), MacOS(ARM64) |
|[v8_r9](https://github.com/ialex32x/GodotJS-Dependencies/releases/download/v8_r9/v8_r9.zip)|v8(12.4.254.20)| v143(14.41.34120)| Windows(x86_64), Linux(x86_64), MacOS(ARM64), Android(ARM64-v8a), iOS(ARM64) |

> [!NOTE]
> Update VS 2022 MSVC toolchain for different pacakge you used to avoid linkage errors.

-----

Why **windows_x86_64_release** does not follow the same naming rules?
> godot 4.3.1 generates `ActiveProjectItemList_` variable name with the path name (see methods.py)
> it'll fail if the path contains '.' or any other characters invalid as variable name
> detect and rename them for better compatibility
