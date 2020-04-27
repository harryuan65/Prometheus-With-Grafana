# GN-Prometheus

## Requirements
Docker Engine + docker-compose

## What can this offer？
監控系統：
 - `Prometheus`: 很方便且整合的監控預警框架 TSDB（Time Series Database）時間序列資料庫，可以搜集各個service的各種metrics
   - `node_exporter`: 監控主機硬體的工具
 - `Grafana`: 精美的儀表板工具
 
 
## How to use ?
1. 你的服務（express server/rails server/go server），設定一個`/metrics`的route
2. 去編輯prometheus.yml
3. 改一下那個yourservice
 - 換成你的service名字（自訂）
 - targets內部改成你的服務網址
4. docker-compose up

localhost:3000
就可以進去grafana設定你要追蹤的資料


