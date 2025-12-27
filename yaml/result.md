|  NAME | PROMT  |DECRIPTION   | EXAMPLE  |
|---|---|---|---|
|  app.yaml | **Requirements:** Use apps/v1 Deployment, set the metadata name to 'main-app', and use a label selector for 'app: web-service'.<br> **Replication:** Set it to 3 replicas for high availability. <br>**Container:** Include a single container using a stable image, and expose port 80 <br> **Constraint:** Keep the manifest minimal and clean so that I can later overlay resource limits, probes, and volume mounts using Kustomize or manual merging. | Create app.yaml manifest    | https://github.com/Vlad1slav1k/AsciiArtify2/blob/main/yaml/app.yaml  |
| app-livenessProbe.yaml  | **Prompt:** "Generate a Kubernetes livenessProbe configuration for a container.<br>**Mechanism:** Use an [HTTP GET / TCP Socket / Exec Command] check.<br>Timing: Set a 30-second initialDelaySeconds to allow for a slow application startup.<br> **Thresholds:** Set it to check every 10 seconds, and only trigger a restart if it fails 5 times in a row. <br>**Thresholds:** Set it to check every 10 seconds, and only trigger a restart if it fails 5 times in a row.   |  Generate a Kubernetes livenessProbe configuration for a container | https://github.com/Vlad1slav1k/AsciiArtify2/blob/main/yaml/app-livenessProbe.yaml  |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
