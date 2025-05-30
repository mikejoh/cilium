<!-- This file was autogenerated via cilium-bugtool cmdref, do not edit manually-->

## cilium-bugtool

Collects agent & system information useful for bug reporting

```
cilium-bugtool [OPTIONS] [flags]
```

### Examples

```
	# Collect information and create archive file
	$ cilium-bugtool
	[...]

	# Collect and retrieve archive if Cilium is running in a Kubernetes pod
	$ kubectl get pods --namespace kube-system
	NAME                          READY     STATUS    RESTARTS   AGE
	cilium-kg8lv                  1/1       Running   0          13m
	[...]
	$ kubectl -n kube-system exec cilium-kg8lv -- cilium-bugtool
	$ kubectl cp kube-system/cilium-kg8lv:/tmp/cilium-bugtool-243785589.tar /tmp/cilium-bugtool-243785589.tar
```

### Options

```
      --archive                   Create archive when false skips deletion of the output directory (default true)
      --archive-prefix string     String to prefix to name of archive if created (e.g., with cilium pod-name)
  -o, --archiveType string        Archive type: tar | gz (default "tar")
      --config string             Configuration to decide what should be run (default "./.cilium-bugtool.config")
      --dry-run                   Create configuration file of all commands that would have been executed
      --enable-markdown           Dump output of commands in markdown format
      --envoy-dump                When set, dump envoy configuration from unix socket (default true)
      --envoy-metrics             When set, dump envoy prometheus metrics from unix socket (default true)
      --exclude-object-files      Exclude per-endpoint object files. Template object files will be kept
      --exec-timeout duration     The default timeout for any cmd execution in seconds (default 30s)
      --get-pprof                 When set, only gets the pprof traces from the cilium-agent binary
  -h, --help                      help for cilium-bugtool
  -H, --host string               URI to server-side API
      --hubble-metrics            When set, hubble prometheus metrics (default true)
      --hubble-metrics-port int   Port to query for hubble metrics (default 9965)
      --parallel-workers int      Maximum number of parallel worker tasks, use 0 for number of CPUs
      --pprof-debug int           Debug pprof args
      --pprof-port int            Pprof port to connect to. Known Cilium component ports are agent:6060, operator:6061, apiserver:6063 (default 6060)
      --pprof-trace-seconds int   Amount of seconds used for pprof CPU traces (default 180)
  -t, --tmp string                Path to store extracted files. Use '-' to send to stdout. (default "/tmp")
```

### SEE ALSO

* [cilium-bugtool completion](cilium-bugtool_completion.md)	 - Generate the autocompletion script for the specified shell

