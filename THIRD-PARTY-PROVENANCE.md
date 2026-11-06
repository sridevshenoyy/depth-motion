# Third-party components and provenance — preliminary

This file records evidence from the Mac and Windows prototypes. **It is not a complete license or corresponding-source package, and does not certify that either installer is ready for redistribution.** Different components have different licenses and distribution conditions. Release maintainers must review the exact artifacts and provide all required notices, license texts, source, and installation or modification information as applicable. The application itself does not yet have a confirmed release license.

The version inventories below describe the prototypes; `platforms/windows/requirements-windows.lock.txt` and `platforms/mac/requirements-lock-mac.txt` are the fuller Python package inventories. `platforms/windows/Third party notices/` contains collected package notices, but its coverage has not been audited. The Mac build has no comparable complete notices collection in this staging folder.

## Image animation engine

- **DepthFlow 1.0.1** — the DepthFlow project, AGPL-3.0 as declared in its package metadata. [Versioned package and available artifacts](https://pypi.org/project/depthflow/1.0.1/); [upstream source](https://github.com/BrokenSource/DepthFlow); [project metadata](https://github.com/BrokenSource/DepthFlow/blob/main/pyproject.toml).
- **ShaderFlow 0.13.0** — the ShaderFlow project, AGPL-3.0 as declared in its package metadata. [Versioned package and available artifacts](https://pypi.org/project/shaderflow/0.13.0/); [upstream source](https://github.com/BrokenSource/ShaderFlow); [project metadata](https://github.com/BrokenSource/ShaderFlow/blob/main/pyproject.toml).
- These upstream links identify the projects; they alone do not establish that all exact corresponding source and applicable notices for the shipped executables have been provided. The collected Windows notice directory currently has no dedicated DepthFlow or ShaderFlow license directory. Preserve the applicable AGPL text and notices and review the application's combined-work licensing and source-distribution obligations.

## Depth-estimation model

The [Depth Anything V2 Small model](https://huggingface.co/depth-anything/Depth-Anything-V2-Small-hf) is identified by its model card as Apache-2.0. The Windows build documentation pins model revision `5426e4f0f36572d16453bbda7a8389317b1bef99` and bundles the model; the tested Mac cache recorded that same revision, but the Mac build downloads model data on first use rather than documenting a pinned runtime revision. Preserve the model card, applicable license and notices, and verify the actual model files and revision used in any release. [Pinned revision](https://huggingface.co/depth-anything/Depth-Anything-V2-Small-hf/tree/5426e4f0f36572d16453bbda7a8389317b1bef99).

## Media tools

### Windows

- The tested Windows build records FFmpeg/FFprobe `9.0.2-essentials_build-www.gyan.dev`, a static build whose included FFmpeg notice identifies GPL v3 and upstream FFmpeg commit `946fcce07b`. [Build supplier's 9.0.2 release](https://github.com/GyanD/codexffmpeg/releases/tag/9.0.2); [recorded FFmpeg source commit](https://github.com/FFmpeg/FFmpeg/commit/946fcce07b); [FFmpeg licensing information](https://ffmpeg.org/legal.html).
- `platforms/windows/Third party notices/FFmpeg/` contains the supplier's notice, version list, and license text. `platforms/windows/BUILD-PROVENANCE.json` records archive and executable SHA-256 hashes. The build contains many statically linked external libraries; the repository staging area does not contain a verified complete set of their exact corresponding sources, patches, license texts, and build scripts. The supplier's FFmpeg commit link alone has not been verified as sufficient for every component.

### Mac

- The tested Mac `ffmpeg` executable reports FFmpeg **9.0** with `--enable-gpl` and many enabled external libraries including x264 and x265. It matches the binary installed by [imageio-ffmpeg 0.8.1](https://pypi.org/project/imageio-ffmpeg/0.8.1/) with SHA-256 `591260c945d0eef150e3bf82b0ef988bd36a9cecc18ff05d6679617159f0a95e`. Its exact corresponding source, any patches, external-library sources, and reproducible build scripts have not yet been assembled or verified.
- The tested Mac `ffprobe` executable reports FFmpeg **8.1.2**; its SHA-256 is `89cf4f93b4bf05e20171270c011ab8ab0d92e50094c6b45d72bcc8e7d72d8f94`. It matches a locally built Podclip ffprobe. The prior build's provenance describes unmodified [FFmpeg 8.1.2 source](https://ffmpeg.org/releases/ffmpeg-8.1.2.tar.xz), archive SHA-256 `464beb5e7bf0c311e68b45ae2f04e9cc2af88851abb4082231742a74d97b524c`, and a separate build script. The archive and script are not yet included in this staging folder. Confirm their applicability and include or offer all material required for the actual release.

## Other dependencies

Both builds list PySide6 Essentials 6.12.0, PyTorch 2.15.0, torchvision 0.29.2 and Transformers 5.22.1, along with other Python and native dependencies. Their applicable license texts and third-party components need review individually; Qt/PySide may have additional LGPL obligations depending on how they are used and distributed. Do not infer that the presence of a collected notice directory establishes compliance. Primary project references: [Qt for Python / PySide](https://doc.qt.io/qtforpython-6/), [PyTorch](https://github.com/pytorch/pytorch), [Transformers](https://github.com/huggingface/transformers).

## Outstanding release work

1. Audit the exact distributed Mac and Windows binaries and model artifacts against their complete dependency inventories.
2. Obtain and preserve the exact corresponding source, modifications and build/install materials required for the distributed AGPL/GPL components, including the FFmpeg-linked libraries; make these available using a legally appropriate distribution mechanism.
3. Add all required license texts, copyright notices, attribution and modification notices for both platforms; verify Qt/PySide and model obligations.
4. Determine and document the license applicable to the application and its source, including compatibility with integrated components.
5. Rebuild and verify that the audited source and notices correspond to the installers actually published. Seek qualified open-source licensing advice where needed.
