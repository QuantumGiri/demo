Name:             integrafe-deployment-one-master-67567f96c6-d9fvw
Namespace:        integrafe-dev
Priority:         0
Service Account:  integrafe-deployment-one
Node:             nonpci-workload-md-1-mx9vd-pxxsl/10.111.88.99
Start Time:       Thu, 19 Dec 2024 14:06:10 +0000
Labels:           admission.datadoghq.com/enabled=true
                  app=integrafe-deployment-one
                  app.kubernetes.io/instance=integra-fe-deployment-one
                  app.kubernetes.io/managed-by=Helm
                  app.kubernetes.io/name=integrafe-deployment-one
                  helm.sh/chart=pgid-integrafe-deployment-chart-1.0.26
                  pod-template-hash=67567f96c6
                  tags.datadoghq.com/businessUnit=Payments-Authorisations
                  tags.datadoghq.com/env=k8s-dev-nonpci
                  tags.datadoghq.com/level1=TBC
                  tags.datadoghq.com/level2=TBC
                  tags.datadoghq.com/level3=3C
                  tags.datadoghq.com/service=integrafe-deployment-one
                  tags.datadoghq.com/version=
Annotations:      ad.datadoghq.com/pgid-integrafe-deployment-chart.logs: [{"source": "ignore"}]
                  admission.datadoghq.com/java-lib.version: v1.34.0
                  cluster-autoscaler.kubernetes.io/safe-to-evict-local-volumes: datadog-auto-instrumentation,datadog-auto-instrumentation-etc
Status:           Running
IP:               10.101.19.239
IPs:
  IP:           10.101.19.239
Controlled By:  ReplicaSet/integrafe-deployment-one-master-67567f96c6
Init Containers:
  datadog-init-apm-inject:
    Container ID:  containerd://817579073b1f2b47bb6b8cc2dd2d70328b8319a9f2d2363bd3dc24d3848b1d25
    Image:         public.ecr.aws/datadog/apm-inject:0
    Image ID:      public.ecr.aws/datadog/apm-inject@sha256:d7f617278d0971cc33ce37e84fedc18bbc8585fc5eb1a2248f5a0fcf0cab09e4
    Port:          <none>
    Host Port:     <none>
    Command:
      /bin/sh
      -c
      --
    Args:
      cp -r /opt/datadog-packages/datadog-apm-inject/* /datadog-inject && echo /opt/datadog-packages/datadog-apm-inject/stable/inject/launcher.preload.so > /datadog-etc/ld.so.preload && echo $(date +%s) >> /datadog-inject/c-init-time.datadog-init-apm-inject
    State:          Terminated
      Reason:       Completed
      Exit Code:    0
      Started:      Thu, 19 Dec 2024 14:06:11 +0000
      Finished:     Thu, 19 Dec 2024 14:06:12 +0000
    Ready:          True
    Restart Count:  0
    Limits:
      cpu:     50m
      memory:  104857600
    Requests:
      cpu:     50m
      memory:  104857600
    Environment:
      DD_INSTRUMENTATION_INSTALL_ID:    c16df2f2-0e63-48a0-af4b-759b74d4609f
      DD_INSTRUMENTATION_INSTALL_TIME:  1730929239
      DD_VERSION:
      DD_SERVICE:                       integrafe-deployment-one
      DD_ENV:                           k8s-dev-nonpci
      DD_INTERNAL_POD_UID:               (v1:metadata.uid)
      DD_EXTERNAL_ENV:                  it-true,cn-datadog-init-apm-inject,pu-$(DD_INTERNAL_POD_UID)
      DD_ENTITY_ID:                      (v1:metadata.uid)
      DD_AGENT_HOST:                     (v1:status.hostIP)
    Mounts:
      /datadog-etc from datadog-auto-instrumentation-etc (rw)
      /datadog-inject from datadog-auto-instrumentation (rw,path="opt/datadog-packages/datadog-apm-inject")
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-nx4x6 (ro)
  datadog-lib-java-init:
    Container ID:  containerd://170260dc1e74000d9759af1d9ec076a35026308faa03b69e0132fda1eac0b0f8
    Image:         public.ecr.aws/datadog/dd-lib-java-init:v1.34.0
    Image ID:      public.ecr.aws/datadog/dd-lib-java-init@sha256:b286e033b49674e720d24580fa7f56ec910953d22ffd4d95b971f0fdd24296ad
    Port:          <none>
    Host Port:     <none>
    Command:
      /bin/sh
      -c
      --
    Args:
      sh copy-lib.sh /datadog-lib && echo $(date +%s) >> /opt/datadog-packages/datadog-apm-inject/c-init-time.datadog-lib-java-init
    State:          Terminated
      Reason:       Completed
      Exit Code:    0
      Started:      Thu, 19 Dec 2024 14:06:13 +0000
      Finished:     Thu, 19 Dec 2024 14:06:13 +0000
    Ready:          True
    Restart Count:  0
    Limits:
      cpu:     50m
      memory:  104857600
    Requests:
      cpu:     50m
      memory:  104857600
    Environment:
      DD_INSTRUMENTATION_INSTALL_ID:    c16df2f2-0e63-48a0-af4b-759b74d4609f
      DD_INSTRUMENTATION_INSTALL_TIME:  1730929239
      DD_VERSION:
      DD_SERVICE:                       integrafe-deployment-one
      DD_ENV:                           k8s-dev-nonpci
      DD_INTERNAL_POD_UID:               (v1:metadata.uid)
      DD_EXTERNAL_ENV:                  it-true,cn-datadog-lib-java-init,pu-$(DD_INTERNAL_POD_UID)
      DD_ENTITY_ID:                      (v1:metadata.uid)
      DD_AGENT_HOST:                     (v1:status.hostIP)
    Mounts:
      /datadog-lib from datadog-auto-instrumentation (rw,path="opt/datadog/apm/library/java")
      /opt/datadog-packages/datadog-apm-inject from datadog-auto-instrumentation (rw,path="opt/datadog-packages/datadog-apm-inject")
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-nx4x6 (ro)
Containers:
  pgid-integrafe-deployment-chart:
    Container ID:   containerd://849e0e7e440df1e275b65a9c5b4a53d0b12c9d71c95f6e25dd87dab1e2da024f
    Image:          ghcr.io/weareplanet/pgid-integrafe:3.5.3.0-snapshot
    Image ID:       ghcr.io/weareplanet/pgid-integrafe@sha256:238947047d4d1eed520dca46da891cb3e6d6b6927b5b307ee2cb5bde2dcd7944
    Ports:          5701/TCP, 5100/TCP, 10110/TCP, 10320/TCP, 20110/TCP, 20111/TCP, 20410/TCP, 30110/TCP, 30111/TCP, 8080/TCP, 21110/TCP, 11200/TCP, 11100/TCP
    Host Ports:     0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP, 0/TCP
    State:          Waiting
      Reason:       CrashLoopBackOff
    Last State:     Terminated
      Reason:       Error
      Exit Code:    1
      Started:      Fri, 24 Jan 2025 05:58:10 +0000
      Finished:     Fri, 24 Jan 2025 05:58:10 +0000
    Ready:          False
    Restart Count:  3914
    Limits:
      cpu:     1
      memory:  4Gi
    Requests:
      cpu:      200m
      memory:   512Mi
    Liveness:   http-get http://:8080/integra/admin/health delay=10s timeout=1s period=45s #success=1 #failure=3
    Readiness:  http-get http://:8080/integra/admin/health delay=10s timeout=1s period=45s #success=1 #failure=3
    Environment:
      DD_INSTRUMENTATION_INSTALL_TYPE:                  k8s_lib_injection
      DD_INSTRUMENTATION_INSTALL_ID:                    c16df2f2-0e63-48a0-af4b-759b74d4609f
      DD_INSTRUMENTATION_INSTALL_TIME:                  1730929239
      DD_SERVICE:                                       integrafe-deployment-one
      DD_INTERNAL_POD_UID:                               (v1:metadata.uid)
      DD_EXTERNAL_ENV:                                  it-false,cn-pgid-integrafe-deployment-chart,pu-$(DD_INTERNAL_POD_UID)
      DD_ENTITY_ID:                                      (v1:metadata.uid)
      DD_AGENT_HOST:                                     (v1:status.hostIP)
      opentelemetry_exporter_enabled:                   false
      ROOT_LOG_LEVEL:                                   error
      COM_LOG_LEVEL:                                    error
      ORG_LOG_LEVEL:                                    error
      key_vault_baseUrl:                                http://172.17.14.175:8080/keyvault
      check_preload_device_keystores_enabled:           true
      key_vault_download_timeoutSecs:                   30
      ENABLE_HAZELCAST:                                 true
      ENABLE_HAZELCAST:                                 true
      JAVA_TOOL_OPTIONS:                                -javaagent:/opt/cccintegra/opentelemetry-javaagent/opentelemetry-javaagent.jar -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=*:8000 -XX:MaxRAMPercentage=100.0 -XX:InitialRAMPercentage=50.0
      torque_dsfactory_cccintegra_connection_password:  <set to the key 'sqlServerPassword' in secret 'integra-fe-deployment-one-properties-secret'>                                Optional: false
      TaskUploadEvents_certificateStorePassword:        <set to the key 'taskUploadEvents_certificateStorePassword' in secret 'integra-fe-deployment-one-properties-secret'>        Optional: false
      TaskUploadTransactions_certificateStorePassword:  <set to the key 'taskUploadTransactions_certificateStorePassword' in secret 'integra-fe-deployment-one-properties-secret'>  Optional: false
      ProtocolDcc_certificateStorePassword:             <set to the key 'protocolDcc_certificateStorePassword' in secret 'integra-fe-deployment-one-properties-secret'>             Optional: false
      Application_encryption_key:                       <set to the key 'application_encryption_key' in secret 'integra-fe-deployment-one-properties-secret'>                       Optional: false
      DD_ENV:                                            (v1:metadata.labels['tags.datadoghq.com/env'])
      DD_VERSION:                                        (v1:metadata.labels['tags.datadoghq.com/version'])
      OTEL_SERVICE_NAME:                                integrafe-deployment-one
      OTEL_K8S_NAMESPACE:                               integrafe-dev (v1:metadata.namespace)
      OTEL_K8S_NODE_NAME:                                (v1:spec.nodeName)
      OTEL_K8S_POD_NAME:                                integrafe-deployment-one-master-67567f96c6-d9fvw (v1:metadata.name)
      HOST_IP:                                           (v1:status.hostIP)
      OTEL_EXPORTER_OTLP_ENDPOINT:                      http://$(HOST_IP):4317
      OTEL_EXPORTER_OTLP_PROTOCOL:                      grpc
      OTEL_RESOURCE_ATTRIBUTES:                         service.name=$(OTEL_SERVICE_NAME), k8s.namespace.name=$(OTEL_K8S_NAMESPACE), k8s.node.name=$(OTEL_K8S_NODE_NAME), k8s.pod.name=$(OTEL_K8S_POD_NAME), k8s.container.name=pgid-integrafe-deployment-chart, host.name=$(OTEL_K8S_NODE_NAME), env=k8s-dev-nonpci
      SERVICE_NAME:                                     integrafe-deployment-one-tcp
      NAMESPACE:                                        integrafe-dev
      LD_PRELOAD:                                       /opt/datadog-packages/datadog-apm-inject/stable/inject/launcher.preload.so
      DD_INJECT_SENDER_TYPE:                            k8s
      DD_INJECT_START_TIME:                             1734617170
    Mounts:
      /etc/ld.so.preload from datadog-auto-instrumentation-etc (ro,path="ld.so.preload")
      /opt/datadog-packages/datadog-apm-inject from datadog-auto-instrumentation (ro,path="opt/datadog-packages/datadog-apm-inject")
      /opt/datadog/apm/library from datadog-auto-instrumentation (rw,path="opt/datadog/apm/library")
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-nx4x6 (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True
  Initialized                 True
  Ready                       False
  ContainersReady             False
  PodScheduled                True
Volumes:
  kube-api-access-nx4x6:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
  datadog-auto-instrumentation:
    Type:       EmptyDir (a temporary directory that shares a pod's lifetime)
    Medium:
    SizeLimit:  <unset>
  datadog-auto-instrumentation-etc:
    Type:        EmptyDir (a temporary directory that shares a pod's lifetime)
    Medium:
    SizeLimit:   <unset>
QoS Class:       Burstable
Node-Selectors:  cluster-node-role=3c
Tolerations:     cluster-node-role=3c:NoSchedule
                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                 node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
                 org.com/role=service:NoSchedule
Events:
  Type     Reason   Age                      From     Message
  ----     ------   ----                     ----     -------
  Warning  BackOff  3m57s (x96426 over 13d)  kubelet  Back-off restarting failed container pgid-integrafe-deployment-chart in pod integrafe-deployment-one-master-67567f96c6-d9fvw_integrafe-dev(5702b6f6-7ab0-4fab-8f5a-ebe600807c92)









pods_status=$(kubectl get pods --all-namespaces -o custom-columns="NAMESPACE:.metadata.namespace,POD:.metadata.name,STATUS:.status.phase,CONTAINERS:.status.containerStatuses[*].state.waiting.reason" --no-headers)
