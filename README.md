# rocm + Tailscale + Prometheus 



Add your ts auth key to .env file and run docker compose
```
cp .env.example .env
# edit the .env file....
docker compose up -d
```

add to prometheus.yaml
```
  - job_name: 'rocm-metrics'
    static_configs:
      - targets: ['workstation-metrics:5000']
    scrape_interval: 15s
    metrics_path: /metrics
```
