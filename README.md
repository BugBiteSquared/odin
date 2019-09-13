# Odin
## A Multiplayer FPS Built From Scratch

### Requirements
 * Vulkan SDK
 * Vulkan-compatible graphics hardware & up-to-date drivers
 * Visual Studio 2017+
 
This is a fork of the code repo for this excellent series of articles on network programming.
http://www.codersblock.org/blog/multiplayer-fps-part-1

## Things done to get original repo working
Change project working directory to odin/data.
Change Vulkan lib directories to "Lib32" for Win32 configs & "Lib" for x64 configs.
Turn off **warning treated as error** for all configs. Not a long term fix, but it gets the app building.

## Further Problems
Shader validation errors are triggering breakpoints:
```
[graphics::vulkan::Validation]  [ UNASSIGNED-CoreValidation-Shader-InconsistentSpirv ] Object: VK_NULL_HANDLE (Type = 0) | SPIR-V module not valid: Vulkan spec doesn't allow BuiltIn VertexId/InstanceId to be used.
  %gl_VertexID = OpVariable %_ptr_Input_int Input

odin.exe has triggered a breakpoint.

[graphics::vulkan::Validation]  [ UNASSIGNED-CoreValidation-Shader-InconsistentSpirv ] Object: VK_NULL_HANDLE (Type = 0) | SPIR-V module not valid: In the Vulkan environment, the OriginLowerLeft execution mode must not be used.
  OpExecutionMode %main OriginLowerLeft

odin.exe has triggered a breakpoint.
```

These can be "continued" through & the app will seemingly run just fine afterwards. Need to fix those validation errors at one point.
