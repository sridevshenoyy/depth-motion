# Contributing

Contributions and bug reports are welcome. Please describe the operating system, app version, what you tried, and any error messages. Remove personal file paths and private media from anything you share publicly.

1. Fork the repository and create a branch.
2. Modify the platform source under `platforms/mac` or `platforms/windows` as appropriate. These builds differ; do not assume changes in one automatically apply to the other.
3. Run the applicable tests and describe what was tested, including whether the packaged application was tested.
4. Submit a pull request explaining the change and any remaining limitations.

The timeline parser tests can be run from either platform source folder with `python -m unittest core.test_timeline -v`. Rendering and packaging require the dependencies and graphics support described in each platform's notes.

The project source is offered under AGPL-3.0-only; third-party components have their own licenses. See `THIRD-PARTY-PROVENANCE.md` for known distribution-review gaps. Do not commit model weights, binary media tools, installers, private images, XML files containing private paths, or generated videos.
