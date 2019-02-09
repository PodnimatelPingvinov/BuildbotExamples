## Buildbot examples
Examples of configuration files for [Buildbot](https://buildbot.net/).
* `minimal.cfg` - just simple example which performs basic project setup.
* `mail_multiple_commits.cfg` - send one email with summary of multiple commit builds.
* `worker_as_a_code.cfg` - store build environment in *.buildbot* file along with project source code. *.buildbot* file must be in JSON format. Example:
```
{
"workers": ["stretch32", "wheezy32"]
}
```
* `pipeline_as_a_code.cfg` - store build pipeline in *.buildbot* file along with project source code. *.buildbot* file must have following format:
```
<workdir> <command with arguments>
...
<workdir> <command with arguments>
```
Example:
```
. rm -rf build
. mkdir build
build cmake ../sources
build make
build ctest
```
