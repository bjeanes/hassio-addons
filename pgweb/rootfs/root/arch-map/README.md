This maps the Home Assistant Add-on architecture strings to the suffix used by pgweb maintainer on their releases

I don't have an understanding of the various ARM types and the labels which pgweb uses (which appear to come from [gox](https://github.com/mitchellh/gox) or perhaps Golang) do not map to those which Docker and HA use. Because I don't understand the distinction nor have the understanding to test, I am only building x86 and amd64 builds for now.

Add a file to this directory and uncomment the appropriate `arch` option in `config.yaml` to contribute a build for these other architectures.
