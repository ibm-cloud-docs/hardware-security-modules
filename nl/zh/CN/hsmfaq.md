---
copyright:
  years: 1994, 2018
lastupdated: "2018-05-07"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IBM Cloud HSM 常见问题
 {{site.data.keyword.cloud}} HSM 产品使用硬件安全模块 (HSM) 将专用的单租户加密、密钥管理和存储作为“即服务”提供。
{:shortdesc}

## 我应该订购哪个版本的 IBM Cloud HSM？
大多数情况下，您应该始终订购最新版本的 HSM。如果一些用户使用的是现有的较旧版本的 HSM，那么可能在高可用性方面会遇到兼容性问题。如果您已经有较旧版本的 HSM，联系支持人员来确定哪个版本适合您。

## 可以将现有 HSM 迁移到新版本吗？
HSM 无法进行迁移。请改为从**设备**菜单中取消现有 HSM，然后订购新版本。

## 什么是硬件安全模块 (HSM)？
HSM 是一个硬件，用于处理加密操作，并且不允许加密密钥离开安全的加密环境。不管是共享的数据、存储的数据还是动态数据，都会在数据创建时进行加密，公司可以在云中执行和维护自己的数据保护策略。 

## IBM Cloud 在哪些方面依赖 HSM？ 
IBM 在 IBM Cloud HSM 7.0 上利用了 Gemalto 的 SafeNet Luna Network HSM 技术。通过此解决方案，客户可以轻松访问世界各地的 60 个 IBM 数据中心，并使用数据中心来解决合规性和数据主权难题。 

## IBM Cloud HSM 通过了 FIPS 认证吗？ 
是的，IBM Cloud HSM 7.0 通过了 FIPS 140-2 3 级认证，旨在确保企业获得可靠、安全的解决方案来管理自己的加密资产。IBM Cloud HSM 6.0 通过了 FIPS 140-2 2 级认证，符合相关的 PKI、数字签名和密钥存储要求。 

## IBM Cloud HSM 可以用来处理哪些用例？
可以使用 HSM 服务来支持各种用例和应用程序，例如公用密钥基础架构 (PKI)、代码签名、数据库加密、文档签名、数字权利管理 (DRM)、认证和授权以及事务处理。
