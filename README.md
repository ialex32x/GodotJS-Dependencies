# GodotJS-Dependencies
Workflows to build all dependencies of GodotJS (v8 and libwebsockets).


- https://github.com/actions/runner-images
- https://github.com/actions/checkout
- https://github.com/actions/create-release

-----

Why **windows_x86_64_release** does not follow the same naming rules?
> godot 4.3.1 generates `ActiveProjectItemList_` variable name with the path name (see methods.py)
> it'll fail if the path contains '.' or any other characters invalid as variable name
> detect and rename them for better compatibility
