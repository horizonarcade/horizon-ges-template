# GoldenEye: Source — AMP Generic Module template

A [CubeCoders AMP](https://cubecoders.com/AMP) Generic Module template that deploys a
**GoldenEye: Source** dedicated server. On Linux it runs the Windows `srcds.exe` under Wine + Xvfb
(GE:S has no native Linux binary), installs the Source 2007 base via SteamCMD (App 310), and fetches
the `gesource` mod automatically from ModDB.

## Install

In AMP: **Configuration → Instance Deployment → Add → Configuration Repository**, enter
`horizonarcade/horizon-ges-template:main`, click **Fetch**, refresh, then
**Create Instance → GoldenEye: Source**.

Create the instance **with Docker** (it uses `cubecoders/ampbase:wine-stable`), then **Update** and
**Start**. See the project's `DEPLOYMENT.md` for ports, configuration, and gameplay rotation.

## Files

| File | Purpose |
|---|---|
| `manifest.json` | Repository manifest (required for AMP to load the templates) |
| `goldeneye-source.kvp` | Main template: launch command, ports, RCON, environment |
| `goldeneye-sourceconfig.json` | Settings shown in the AMP panel |
| `goldeneye-sourcemetaconfig.json` | Empty — settings are passed on the command line |
| `goldeneye-sourceports.json` | Port definitions |
| `goldeneye-sourceupdates.json` | Install/update stages (SteamCMD, Wine init, mod fetch) |

## License & attribution

These template files are released under the **MIT License** (see `LICENSE`).

The license covers **only these AMP template/config files**. It does **not** cover GoldenEye: Source
itself — GE:S is a separate, non-commercial fan project owned by the GoldenEye: Source Team
(<https://www.geshl2.com/>). This template only downloads GE:S from its official distribution
(ModDB) and does not redistribute the game's code or assets. AMP is a product of CubeCoders Ltd.
