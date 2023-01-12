# build-re-target - Build a Re project in GitHub Actions

This action builds your project using the [Re build system](https://github.com/osdeverr/rebs).

### Usage

```yaml
jobs:
  example:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout
      uses: actions/checkout@v3

    # You have to set up the Re environment once before running any Re actions.
    - name: Setup Re
      uses: osdeverr/actions-setup-re@v2

    # The action will fail if anything goes wrong with the build.
    # All of the project's dependencies will get automatically loaded.
    - name: Build
      uses: osdeverr/actions-build-re-target@v2

      # All of the following parameters are optional
      with:        
        path: .
        targets: hello-world libhello istuffclientdelegate

        arch: x64
        configuration: debug
```

**NOTE:** You have to set up Re using [osdeverr/actions-setup-re](https://github.com/osdeverr/actions-setup-re) before you can use this action!
