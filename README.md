# repository-idtxcore-unity-natives

Windows x86_64 native plugins for the `com.vsekai.idtxcore` Unity package
(`V-Sekai-fire/interactor-flow`, `flow/adapters/unity/IdtxCore`). A repo manifest
checks this repository out as that package's `Plugins/x86_64` folder:

    <project name="interactor-flow" path="interactor-flow" />
    <project name="repository-idtxcore-unity-natives"
             path="interactor-flow/flow/adapters/unity/IdtxCore/Plugins/x86_64" />

| File | What it is |
|---|---|
| `idtx_core.dll` | libidtx_core, the C ABI the package's `[DllImport("idtx_core")]` binds |
| `libidtx_usd.dll` | the V-Sekai OpenUSD schema extension |
| `usd_ms.dll` | OpenUSD 26.05, monolithic build |
| `tbb12.dll` | oneTBB, OpenUSD's threading runtime |
| `usd~/` | OpenUSD plugin registry; `IdtxCoreLoader` puts it on `PXR_PLUGINPATH_NAME`. The `~` keeps Unity from importing it. |

The binaries come unchanged from the `unity-plugin-Windows` artifact of interactor-flow's
Unity Plugin workflow, run 34493483865, built from interactor-flow 27727b04
(`pixi run unity`, the `unity_plugin` scons alias). interactor-flow's later commits up to
323c42a8 change only CI workflows. The `.meta` files are the package's own.

idtx_core and libidtx_usd are Apache-2.0 (`LICENSE`). OpenUSD is under the Tomorrow Open
Source Technology License 1.0 (a modified Apache-2.0) and oneTBB under Apache-2.0; their
license texts ship with their sources.
