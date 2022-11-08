# Repro for `prettier-maven-plugin` issue #74

This is a minimal repro for [issue #74](https://github.com/HubSpot/prettier-maven-plugin/issues/74) in the `prettier-maven-plugin` project.

It contains 2 simple maven project with a Main class containing a single wrongly indented method.

## Steps to reproduce

Clone this repo: `git clone https://github.com/gaetanmaisse/prettier-maven-plugin-issue`

### Check everything works as expected with version 0.17
1. Go to the `version-0.17` folder: `cd version-0.17`
2. Run prettier check: `mvn prettier:check`
3. Observe the following error:

```bash
[ERROR] Failed to execute goal com.hubspot.maven.plugins:prettier-maven-plugin:0.17:check (default-cli) on project version-0.17: Code formatting issues found, please run prettier-java -> [Help 1]
```

### Try with version 0.18
1. Go to the `version-0.18` folder: `cd version-0.18`
2. Run prettier check: `mvn prettier:check`
3. Observe no error, even though the code is still wrongly indented



4. Run pettier check in sudo mode: `sudo mvn prettier:check`
5. Observe the following error:

```bash
[ERROR] Failed to execute goal com.hubspot.maven.plugins:prettier-maven-plugin:0.18:check (default-cli) on project version-0.18: Code formatting issues found, please run prettier-java -> [Help 1]
```
