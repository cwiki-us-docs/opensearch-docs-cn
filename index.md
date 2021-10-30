---
layout: default
title: Get started
nav_order: 1
redirect_from: /404.html
permalink: /
---

# OpenSearch 文档

本站点是有关 [OpenSearch](https://opensearch.org/) 相关的技术文档。

OpenSearch 是基于 Apache 2.0 许可证进行开发的搜索，分析和可视化组件，在 OpenSearch 中提供了高级安全特性，警告，SQL 支持，自动索引管理，深度性能分析等功能。

[Get started](#docker-quickstart){: .btn .btn-blue }


---

## 为什么使用 OpenSearch?

OpenSearch 是一个高效维护的套件，通常被用于下面的一些情况：

* 日志分析（Log analytics）
* 实时应用监控（Real-time application monitoring）
* 点击流分析（Clickstream analytics）
* 后台查询（Search backend）

组件 | 目的
:--- | :---
[OpenSearch]({{site.url}}{{site.baseurl}}/opensearch/) | 数据存储和搜索引擎
[OpenSearch 面板（OpenSearch Dashboards）]({{site.url}}{{site.baseurl}}/dashboards/) | 搜索前台可视化界面
[安全（Security）]({{site.url}}{{site.baseurl}}/security-plugin/) | 针对集群的授权和访问控制
[报警（Alerting）]({{site.url}}{{site.baseurl}}/monitoring-plugins/alerting/) | 当你的数据达到某个阈值后获得通知
[SQL]({{site.url}}{{site.baseurl}}/search-plugins/sql/) | 使用 SQL 或者管道处理语言（piped processing language）来对你的数据进查询
[索引状态管理（Index State Management）]({{site.url}}{{site.baseurl}}/im-plugin/) | 自动化的索引操作
[KNN]({{site.url}}{{site.baseurl}}/search-plugins/knn/) | 在你的矢量数据中找到 “nearest neighbors”
[性能分析器（Performance Analyzer）]({{site.url}}{{site.baseurl}}/monitoring-plugins/pa/) | 监控和优化你的集群
[异常侦测（Anomaly detection）]({{site.url}}{{site.baseurl}}/monitoring-plugins/ad/) | 识别非典型数据然后自动收到通知
[异步查询（Asynchronous search）]({{site.url}}{{site.baseurl}}/search-plugins/async/) | 在你的后台搜运行查询请求
[跨集群复制（Cross-cluster replication）]({{site.url}}{{site.baseurl}}/replication-plugin/index/) | 在多个 OpenSearch 集群之间对你的数据进行复制

绝大多数的 OpenSearch 插件都有相对应的 OpenSearch 面板插件，能够提供方便、统一的用户界面。

有关更多本项目的的特性，请参考 [FAQ](https://opensearch.org/faq/) 页面中的内容。


---

## Docker quickstart
Docker
{: .label .label-green }

1. Install and start [Docker Desktop](https://www.docker.com/products/docker-desktop).
1. Run the following commands:

   ```bash
   docker pull opensearchproject/opensearch:{{site.opensearch_version}}
   docker run -p 9200:9200 -p 9600:9600 -e "discovery.type=single-node" opensearchproject/opensearch:{{site.opensearch_version}}
   ```

1. In a new terminal session, run:

   ```bash
   curl -XGET --insecure -u 'admin:admin' 'https://localhost:9200'
   ```

1. [Create]({{site.url}}{{site.baseurl}}/opensearch/rest-api/index-apis/create-index/) your first index.

   ```bash
   curl -XPUT --insecure -u 'admin:admin' 'https://localhost:9200/my-first-index'
   ```

1. [Add some data]({{site.url}}{{site.baseurl}}/opensearch/index-data/) to your newly created index.

   ```bash
   curl -XPUT --insecure -u 'admin:admin' 'https://localhost:9200/my-first-index/_doc/1' -H 'Content-Type: application/json' -d '{"Description": "To be or not to be, that is the question."}'
   ```

1. [Retrieve the data]({{site.url}}{{site.baseurl}}/opensearch/index-data/#read-data) to see that it was added properly.

   ```bash
   curl -XGET --insecure -u 'admin:admin' 'https://localhost:9200/my-first-index/_doc/1'
   ```

1. After verifying that the data is correct, [delete the document]({{site.url}}{{site.baseurl}}/opensearch/index-data/#delete-data).

   ```bash
   curl -XDELETE --insecure -u 'admin:admin' 'https://localhost:9200/my-first-index/_doc/1'
   ```

1. Finally, [delete the index]({{site.url}}{{site.baseurl}}/opensearch/rest-api/index-apis/delete-index).

   ```bash
   curl -XDELETE --insecure -u 'admin:admin' 'https://localhost:9200/my-first-index/'
   ```

To learn more, see [Docker image]({{site.url}}{{site.baseurl}}/opensearch/install/docker/) and [Docker security configuration]({{site.url}}{{site.baseurl}}/opensearch/install/docker-security/).


---

## Installation

For more comprehensive installation instructions for other download types, such as tarballs, see these pages:

- [Install and configure OpenSearch]({{site.url}}{{site.baseurl}}/opensearch/install/)
- [Install and configure OpenSearch Dashboards]({{site.url}}{{site.baseurl}}/dashboards/install/)


## The secure path forward

OpenSearch includes a demo configuration so that you can get up and running quickly, but before using OpenSearch in a production environment, you must [configure the security plugin manually]({{site.url}}{{site.baseurl}}/security-plugin/configuration/index/): your own certificates, your own authentication method, your own users, and your own passwords.


## Looking for the Javadoc?

See [opensearch.org/javadocs/](https://opensearch.org/javadocs/).


## Get involved

[OpenSearch](https://opensearch.org) is supported by Amazon Web Services. All components are available under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0.html) on [GitHub](https://github.com/opensearch-project/).

The project welcomes GitHub issues, bug fixes, features, plugins, documentation---anything at all. To get involved, see [Contributing](https://opensearch.org/source.html) on the OpenSearch website.
