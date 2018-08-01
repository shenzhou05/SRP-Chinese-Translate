# The Render Pipeline Context
SRP renders using the concept of delayed execution. As a user you build up a list of commands and then execute them. The object that you use to build up these commands is called the `ScriptableRenderContext` and is passed as an argument to the Render function.

When you have populated the context with operations, then you can call ‘Submit’ to submit all the queued up rendering calls. These calls will generally be a combination of `CommandBuffer` executions as well as SRP specific draw commands.

An example of this is clearing a render target using a command buffer that is executed by the render context:

```C#
public class BasicPipeInstance : RenderPipeline
{
    private Color m_ClearColor = Color.black;

    public BasicPipeInstance(Color clearColor)
    {
        m_ClearColor = clearColor;
    }

    public override void Render(ScriptableRenderContext context, Camera[] cameras)
    {
        // does not so much yet :(
        base.Render(context, cameras);

        // clear buffers to the configured color
        var cmd = new CommandBuffer();
        cmd.ClearRenderTarget(true, true, m_ClearColor);
        context.ExecuteCommandBuffer(cmd);
        cmd.Release();
        context.Submit();
    }
}
```

More details about what can be achieved via the context can be found here: https://docs.unity3d.com/ScriptReference/Experimental.Rendering.ScriptableRenderContext.html