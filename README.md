# CFPS: LTE Redirection Attack

Patches used in research experimenting with LTE.

## `openbts`

Patch names correspond to respective (sub)repository name.
Use at your own risk, `OpenBTS` crashes on exit.

Commit 480f65d of [RangeNetworks/dev](https://github.com/RangeNetworks/dev)

## `uhd`
Patches to get version 3.15 to build (srsRAN doesn't support later versions).
Earlier versions (3.14.1) need more work.

Repo: [EttusResearch/uhd](https://github.com/EttusResearch/uhd)

## `srsran`
Attack code, based on the `agpl_next` branch (commit 6a3b925) of
[srsran/srsRAN](https://github.com/srsran/srsRAN)

## `unused`
Incomplete srsRAN backend for libiio (for ADALM PLUTO); libiio lacks timestamp support
