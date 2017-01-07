# Rust AppVeyor Configuration and Scripts

How to setup AppVeyor CI (a windows CI service) for Rust projects:

1. Create a new AppVeyor project for your repository. See the Appveyor documentation on how to add
   your project to Appveyor.
2. Copy `appveyor.yml` into the repository root directory.
3. Configure `appveyor.yml` as needed for project. The default template is sufficient for a basic
   Rust project that builds on both 32-bit and 64-bit windows targets for both MSVC and GNU
   toolchains across all three Rust channels (stable, beta, and nightly).
4. Commit the appveyor files. AppVeyor will automatically pick up the configuration (unless the
   project is configured to ignore `appveyor.yml` files) and perform the builds.

## AppVeyor Rust Support

AppVeyor is intended mainly for msbuild-style builds, and Rust is not included on the AppVeyor VMs.
The `appveyor.yml` script uses Rustup to automatically install Rust for each target and channel in
the build matrix.

See the comments in `appveyor.yml` for more details on configuring and installing Rust in AppVeyor,
or configuring the build matrix for your specific project needs (e.g. unstable feature flags).

## License

These scripts are distributed under the terms of the Free Public License, which allows you to use,
copy, modify, and/or distribute these files for any purpose without any restrictions, attribution,
or notices, so can be used in your projects without any license obligation burdens.

See [LICENSE](LICENSE) for details.