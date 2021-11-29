# JInfoFlow-bench
JInfoFlow-bench is a taint analysis benchmark suite containing 12 plain Java benchmarks exercising reflection, event-driven architecture, and popular software engineering patterns.

# Building
```
./gradlew fatJar
```

# Benchmarking with the P/Taint and Doop framework
```
./doop --platform java_7 -i <JInfoFlow-bench>/build/libs/JInfoFlow-bench-all-1.0-SNAPSHOT.jar --information-flow minimal --distinguish-all-string-buffers -main <mainclass> -a selective-2-object-sensitive+heap --reflection-classic --reflection-high-soundness-mode
```


where `<mainclass>` is one of the following:
```
org.clyze.JInfoFlowBench.application.event_based.Events1
...event_based.Events2
...event_based.Events3
...event_based.Events4
...event_based.Events5
...basic.Substrings
...basic.Arrays
...ctx_sensitivity_only.StaticMethods
...ctx_sensitivity_only.InstanceMethods
...ctx_sensitivity_only.InstanceAndStaticMethods
...ctx_sensitivity_only.OverwriteSources
...ctx_sensitivity_only.OverwriteSinks
```
