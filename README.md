# Build Autotools Project

This action builds an autotools project using the `autoreconf` -> `configure` -> `build` cycle.

# Usage

```yaml
- uses: wolfSSL/actions-build-autotools-project@v1
  with:
    # Parameters to be used in the actions/checkout step. See
    # https://github.com/actions/checkout for details on how
    # to use these parameters.
    repository: ''
    ref: ''
    # This parameter is also used as the build directory. This
    # is useful when building multiple projects in one action.
    path: ''

    # The arguments passed to the ./configure script.
    configure: ''

    # Whether or not make check should be run on the build.
    # Default: true
    check: ''

    # Whether or not make install should be run on the build.
    # Installs to $GITHUB_WORKSPACE/build-dir by default.
    # Default: false
    install: ''

    # The patch file to use when we are building an OSP project.
    patch-file: ''

    # The user_settings.h file to copy in when when building.
    user-settings: ''
```

# Example

```yaml
- name: Build, test, and install wolfSSL
  uses: wolfSSL/actions-build-autotools-project@v1
  with:
    repository: wolfSSL/wolfssl
    ref: master
    path: wolfssl
    configure: --enable-all
    check: true
    install: true
```

