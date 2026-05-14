# IBM Bob Support

Support for [IBM Bob](https://bob.ibm.com/) at [https://github.com/mathieucarbou-ibm/graphify](https://github.com/mathieucarbou-ibm/graphify) 

## Install graphify with IBM Bob support

```bash
mat@LF32KQLV6P ~/Downloads
> uv tool install git+https://github.com/mathieucarbou-ibm/graphify.git@ibm-bob
> graphify install --platform bob
```

## Uninstall graphify

```bash
mat@LF32KQLV6P ~/Downloads
> graphify uninstall
```

## Generate a graph

```bash
mat@LF32KQLV6P ~/Workspace/terracotta-ehcache3
> bob -i "/graphify ."
```

## Update a graph

```bash
mat@LF32KQLV6P ~/Workspace/terracotta-ehcache3
> bob -i "/graphify . --update"
```

## Query a graph

```bash
mat@LF32KQLV6P ~/Workspace/terracotta-ehcache3
> bob -i "/graphify query 'what are cache tiers and how they work ?'"
```

## Add the graph to the global graph 

The global graph is at `~/.graphify/global-graph.json`.

```bash
mat@LF32KQLV6P ~/Workspace/terracotta-ehcache3
> graphify global add ./graphify-out/graph.json --as terracotta-ehcache3
```

## List the content of the global graph

```bash
mat@LF32KQLV6P ~/Downloads
> graphify global list
```

## Query the global graph

```bash
mat@LF32KQLV6P ~/Downloads
> bob -i "/graphify query 'how to configure security in a terracotta server ?' --global"
> bob -i "/graphify query 'how to configure security in a enterprise terracotta server ?' --global"
> bob -i "/graphify query 'how to use config-tool to repair the configuration of some cluster nodes that crashed suring last configuration change ' --global"
> bob -i "/graphify query 'How I can start one pre-activated server and programmatically use the Java management API to query the server statistics ?' --global"
> bob -i "/graphify query 'How I can start one pre-activated server using the server start script (CLI)' --global"
> bob -i "/graphify query 'How to use the programmatic Java management API to query the server statistics through the TMS entity ? Note: skip terracotta-core project for your answer.' --global"
```

## Switch to code mode to implement:

Bob prompt:

```
Implement a Main Java class in this project that is querying the server stats using management java programmatic api and tms entoty, and add a README to write inside the CLI to start the server.
Use Gradle as the build system to compile and run the Main class.
The client libraries can be sourced from the terracotta kit at ~/Workspace/terracotta-enterprise/kit/build/test-kit.
The server script to be started is also in the kit at ~/Workspace/terracotta-enterprise/kit/build/test-kit. 
```
