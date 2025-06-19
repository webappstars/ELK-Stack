# ELK Stack 模板（Docker Compose）

本仓库提供了一个生产可用的 ELK（Elasticsearch、Logstash、Kibana）堆栈 Docker Compose 模板，具备私有网络与独立服务结构。

## 📦 功能特点
- 私有 Docker 网络 (`elknet`)，内部安全通信
- Elasticsearch 数据持久化卷
- 简单示例 Logstash 日志处理管道
- 支持开发环境和生产环境扩展配置

## 🚀 使用方法

```bash
git clone https://github.com/your-username/elk-stack-template.git
cd elk-stack-template
docker-compose -p elk up -d
```

访问地址：
- Elasticsearch: http://localhost:9200
- Kibana: http://localhost:5601

## 📂 目录结构
```
elk-stack-template/
├── docker-compose.yml
├── logstash/
│   ├── config/logstash.yml
│   └── pipeline/logstash.conf
```

## 🔐 生产环境建议
- Elasticsearch 启用认证：`xpack.security.enabled: true`
- 推荐使用 nginx 或 caddy 做反向代理及 TLS 终止
- 敏感配置使用 Docker Secret 或 .env 文件
- 根据需要调整 Elasticsearch 内存：`ES_JAVA_OPTS`

## 📬 联系方式
如需完整生产版本（TLS、认证、CI/CD 部署）可联系维护者获取。