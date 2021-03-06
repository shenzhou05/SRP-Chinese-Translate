Fog is the effect of overlaying a color onto objects depending on their distance from the Camera. This simulates fog or mist in outdoor environments.  The High Definition Render Pipeline (HDRP) provides different methods of producing fog within your Unity Project. HDRP’s [Volume](https://github.com/Unity-Technologies/ScriptableRenderPipeline/wiki/Volumes) framework allows you to easily manage localized fog in different areas of your Scene. To select the type of fog for each Volume, set the Fog **Type** property in the Volume’s [Visual Environment](https://github.com/Unity-Technologies/ScriptableRenderPipeline/wiki/Visual-Environment) override.

HDRP provides the following types of fog:

- [Linear Fog](https://github.com/Unity-Technologies/ScriptableRenderPipeline/wiki/Linear-Fog): Increases fog density linearly with view distance and world space height. This is useful for applying fog to rendering larger, lower priority, areas of your Scene as it is less resource intensive as the other fog types. 
- [Exponential Fog](https://github.com/Unity-Technologies/ScriptableRenderPipeline/wiki/Exponential-Fog): Increases fog density exponentially with view distance and world space height. This fog type offers a more realistic fog effect than linear. 
- [Volumetric Fog](https://github.com/Unity-Technologies/ScriptableRenderPipeline/wiki/Volumetric-Fog): Realistically simulates the interaction of lights with fog, which allows for physically-plausible rendering of glow and crepuscular rays.

