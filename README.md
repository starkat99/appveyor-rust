# Rust AppVeyor Configuration and Scripts

How to setup AppVeyor CI (a windows CI service) for Rust projects:

1. Create a new AppVeyor project for your repository.
2. Copy `appveyor.yml` and `appveyor_rust_install.ps1` into the repository root directory.
3. Configure `appveyor.yml` for project. The default template is sufficient for a basic Rust
   project that builds on every windows target across all three Rust channels.
4. Commit the appveyor files. AppVeyor will automatically pick up the configuration (unless the
   project is configured to ignore `appveyor.yml` files) and perform the builds.

## AppVeyor Rust Support

AppVeyor is intended mainly for msbuild-style builds, and Rust is not included on the AppVeyor VMs.
The `appveyor_rust_install.ps1` script will allow automatic download and installation of Rust for
builds, making it possible to use custom build scripts to run cargo or rustc builds of Rust code.

`appveyor_rust_install.ps1` uses `channel` and `target` environmnet variables (or command-line
arguments) to automatically download and install Rust. Only `pc-windows` targets are supported,
and any Rust distribution channel may be used (stable, beta, or nightly). See the comments in
`appveyor_rust_install.ps1` and `appveyor.yml` for more details on configuring and installing Rust
in AppVeyor.

## License

These scripts are distributed under the terms of the Free Public License, which allows you to use,
copy, modify, and/or distribute these files for any purpose without any restrictions or notices, so
can be used in your projects without any license obligation burdens.

See [LICENSE](LICENSE) for details.