# GN-Prometheus

## Requirements
Docker Engine + docker-compose

## What can this offer？
- 監控系統：
   - `Prometheus`
     - 很方便且整合的監控預警框架 TSDB（Time Series Database）時間序列資料庫，可以搜集各個service的各種metrics
     - 含有`node_exporter`: 監控主機硬體的工具
   - `Grafana`
     - 精美的儀表板工具
 
## How it works?
基本上就是prometheus會搜集資料存起來，然後餵給grafana顯示出來，也可以在這整理dashboard。

## How to use ?
1. 在你的服務（express server/rails server/go server...隨便）設定一個`/metrics`的route
    - 隨便回傳一個key: value `e.g. current_active_users: 45`
2. 去編輯prometheus.yml
3. 改一下那個`yourservice`
   - 換成你的service名字（自訂）
   - `targets`內部改成你的服務網址
4. `docker-compose up`

`localhost:3000`
就可以進去grafana設定你要追蹤的資料  
`選dashboard` -> `建立一個panel` -> `add query` -> `選prometheus` -> `query那邊打上` 
看有沒有剛剛建立的current_active_users: 45

