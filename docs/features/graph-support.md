# Graph Support

| Name                | Formatting    | Node Commands | Notes                                                                     |
|---------------------|---------------|---------------|---------------------------------------------------------------------------|
| ✅ Blueprint         | Blueprint     | Yes           | Any graph type which uses blueprint based nodes                           |
| ✅ Material          | Simple        | Yes           |                                                                           |
| ✅ Mutable           | Simple        | Yes           |                                                                           |
| ✅ Sound Cue         | Simple        | Yes           |                                                                           |
| ✅ Behavior Tree     | Behavior Tree | None          |                                                                           |
| ✅ Environment Query | Behavior Tree | None          |                                                                           |
| ⚠️ PCG              | Simple        | Issues        | Seems to be some issues with disconnecting and linking with node commands |
| ⚠️ Camera Rig       | Simple        | Issues        | Beta plugin, let me know if you are interested in support for this graph  |
| ⚠️ Not Yet Dialogue | Behavior Tree | Untested      | External plugin                                                           |
| ⚠️ Flow Graph       | Simple        | Untested      | External plugin                                                           |
| ❌ Control Rig       | Unsupported   | Unsupported   | Unable to fix issues with this graph type                                 |

**Formatting**: What formatting type is used for the graph

**Node Commands**: Do commands such as delete and link, swap nodes work

!!! note "Auto-formatting"
    Auto-formatting is disabled by default for all non-blueprint graphs