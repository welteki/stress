# Stress

[stress](https://github.com/resurrecting-open-source-projects/stress) tool turned into a function.

Imposes a configurable amount of CPU, memory, I/O, or disk stress on a function pod.

```sh
faas-cli up

# This invocation will impose a memory load of 20Mb for 10 seconds
# on the function pod.
echo "--vm 1 --vm-bytes 20M -t 10" | faas-cli invoke stress
```