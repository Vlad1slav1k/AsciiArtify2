|  NAME | PROMT  |DECRIPTION   | EXAMPLE  |
|---|---|---|---|
|  app.yaml | **Requirements:** Use apps/v1 Deployment, set the metadata name to 'main-app', and use a label selector for 'app: web-service'.<br> **Replication:** Set it to 3 replicas for high availability. <br>**Container:** Include a single container using a stable image, and expose port 80 <br> **Constraint:** Keep the manifest minimal and clean so that I can later overlay resource limits, probes, and volume mounts using Kustomize or manual merging. | Create app.yaml manifest    | https://github.com/Vlad1slav1k/AsciiArtify2/blob/main/yaml/app.yaml  |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
