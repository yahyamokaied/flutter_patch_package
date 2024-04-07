# flutter_patch_package

Dart tool for patching Flutter packages, enabling quick fixes, modifications, and version control integration for a smoother development workflow.

##  Features
* `Instant Patches:` Instantly apply fixes to Flutter packages.

* `Version Alerts:` Receive notifications about version mismatches.

* `Error Logging:` Automatic logging for failed patch attempts ensures you're always informed.


## Installation
  To use this plugin, add `flutter_patch_package` as a [dependency in your pubspec.yaml file](https://flutter.io/platform-plugins/). For example:

```yaml
dependencies:
flutter_patch_package: '^0.0.9'
```


### Usage


* `Clean git working directory:`

    To ensure a clean start before using flutter_patch_package, check your Git status with:

```yaml
git status
```

You should see a message similar to this: `nothing to commit, working tree clean`



* `Start Patching:`

    Navigate to you project directory and execute:

```yaml
flutter patch <package_name> start
```

This command prepares the package for patching by saving a snapshot of its current state for later comparison.


* `Apply Your Changes:`

    Modify the package directly in `.pub-cache` to fix issues or add new functionality.


* `Finalize Patch:`

    This process compares the modified package to the original snapshot, generating a patch file that encapsulates your changes.

    To do this run:

```yaml
flutter patch <package_name> done
```

The generated patch file is stored in the `patches/` directory within your project. 


* `Applying Patches Automatically or Manually`

    `flutter_patch_package` automatically applies patches after each flutter pub get or dart pub get.

    For manual patch application at any time, use:

```yaml
flutter pub run flutter_patch_package
```


* `Review Changes`

    Use `git diff` to examine the modifications. This helps you understand what has been changed by the patch application.


* `Commit Changes`

    If you're satisfied with the updates, commit them to your version control system. This can be done using:


```yaml
git add .
git commit -m "Applied patches to <package_name>"

```


### Version Compatibility Warning:
  flutter_patch_package smartly warns you about any version mismatches, ensuring smooth package upgrades.


### Troubleshooting
  If you encounter errors, refer to the logs/ directory for detailed diagnostics and quick troubleshooting.