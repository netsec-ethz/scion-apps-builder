# scion-apps-builder

Scripts and tools to build SCION apps

## Configuration

CI process relies on some variables defined below. They can be configured using `Settings / CICD / Environment variables`.

### DEB repository configuration

* `CI_SSH_PRIVATE_KEY`

## Usage

For every commit GitLab CI and its artifacts are used to store the output. Each commit triggers a job which will store built packages for a short while in the GitLab Artifactory.

### Manual trigger

Pipeline can be run manually in order to build packages (without releasing them) using `CICD / Pipelines / Run Pipeline`. For a run containing deployment step please read the next chapter.

### Releasing packages

> TODO

## Schedule

The builder is configured to run twice per day in order to check whether the packages can be still created successfuly, but without releasing them. The last step has to be invoked manually by the operator as described above (by pushing a proper tag).

### Debian-based
```bash
echo "deb [trusted=yes] http://packages.netsec.inf.ethz.ch/debian all main" >> /etc/apt/sources.list
```

```bash
apt install -y apt-transport-https
echo "deb [trusted=yes] https://packages.netsec.inf.ethz.ch/debian all main" >> /etc/apt/sources.list
```

### RH-based
Not yet available.

## Upstream projects

* https://github.com/netsec-ethz/scion-apps
