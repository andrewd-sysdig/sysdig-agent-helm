# sysdig-agent-helm
POC User friendly Helm Chart for sysdig-agent

**Note:** this hasn't been implemented (yet) and doesn't container all configuration options. It is just to show an example of a values.yaml that we could use to make the sysdig client side components more user friendly to install

## Examples

### Example 1: Simple example to install the sysdig-agent only
```
helm upgrade sysdig-agent --install --create-namespace --namespace sysdig-agent \
--set clusterName=MyAwesomeK8sCluster \
--set accessKey=202cf289-a0fa-43d3-bf71-09425sc6e0d2 \
--set apiEndpoint=app.au1.sysdig.com \
sysdig/sysdig-agent
```

### Example 2: Install sysdig-agent & new VM runtime scanner only
```
helm upgrade sysdig-agent --install --create-namespace --namespace sysdig-agent \
--set clusterName=MyAwesomeK8sCluster \
--set accessKey=202cf289-a0fa-43d3-bf71-09425sc6e0d2 \
--set apiEndpoint=app.au1.sysdig.com \
--set runtimeScanner.enable=true \
sysdig/sysdig-agent
```

### Example 3: Install sysdig-agent, new VM runtime scanner and KSPM
```
helm upgrade sysdig-agent --install --create-namespace --namespace sysdig-agent \
--set clusterName=MyAwesomeK8sCluster \
--set accessKey=202cf289-a0fa-43d3-bf71-09425sc6e0d2 \
--set apiEndpoint=app.au1.sysdig.com \
--set runtimeScanner.enable=true \
--set kspm.enable=true \
sysdig/sysdig-agent
```

### Example 4: Install sysdig-agent, Legacy Scanning Node Image Analzyer and Legacy Scanning Host Scanner
```
helm upgrade sysdig-agent --install --create-namespace --namespace sysdig-agent \
--set clusterName=MyAwesomeK8sCluster \
--set accessKey=202cf289-a0fa-43d3-bf71-09425sc6e0d2 \
--set apiEndpoint=app.au1.sysdig.com \
--set nodeImageAnalyzer.enable=true \
--set hostAnalyzer.enable=true \
sysdig/sysdig-agent
```

### Example 5: Install sysdig-agent, and all other client components (old and new scanning, benchmark and kspm) and Eve Connector
```
helm upgrade sysdig-agent --install --create-namespace --namespace sysdig-agent \
--set clusterName=MyAwesomeK8sCluster \
--set accessKey=202cf289-a0fa-43d3-bf71-09425sc6e0d2 \
--set apiEndpoint=app.au1.sysdig.com \
--set runtimeScanner.enable=true \
--set kspm.enable=true \
--set nodeImageAnalyzer.enable=true \
--set hostAnalyzer.enable=true \
--set benchmarkRunner.enabled=true \
--set eveConnector.enabled=true \
sysdig/sysdig-agent
```
