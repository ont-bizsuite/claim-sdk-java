# claim-sdk-java

## issuer方法说明

### 初始化设置app域名,颁发者私钥和支付手续费私钥
```
Applicaion.init(String domain, String issuerWif, String payerWif)
```

### 添加颁发claim的模板
```
Applicaion.addClaimTemplate(ClaimTemplate template)
```

### 设置区块链节点
```
Applicaion.setRestfulUrl(String restfulUrl)
```

### 按照模板颁发claim
```
generateClaimByTemplate(String templateId, String ownerOntId, Map<String, Object> properties, Date expireDate)
```

### 按照所给内容颁发claim
```
generateClaim(String ownerOntId, String context, Map<String, Object> properties, Date expireDate)
```

### 吊销claim
```
revokeClaim(String claimId)
```

### 构造用户获取claim参数
```
constructData(String taName, String taIcon)
```

### 构造二维码参数
```
qrCodeParams(String id, String signature, String ownerId, String dataUrl, String callbackUrl, boolean mainNet)
```

### 封装claim的结果集(返回给OntAuth)
```
claimResult(List<ClaimMap> claimList) 
```

### 封装无claim的结果集(返回给OntAuth)
```
noClaimResult()
```

### 颁发者对数据签名
```
sign(String data)
```


## consumer方法说明

### 初始化claim需求者参数(域名，私钥，应用名称，应用图标)
```
Application.init(String domain, String wif, String dappName, String dappIcon)
```

### 添加claim需求模板
```
Application.addClaimConsumer
```

### 设置区块链节点
```
Application.setRestfulUrl(String restfulUrl)
```

### 根据需求模板构造让用户授权claim的参数
```
constructData(String modelId)
```

### 构造二维码参数
```
qrCodeParams(String id, String signature, String ownerId, String dataUrl, String callbackUrl, boolean mainNet)
```

### 应用方对数据签名
```
sign(String data)
```

## 工具类方法说明

### 查询claim状态是否有效
```
ClaimUtility.checkStatus(String claimId)
```

### 获取claim的owner
```
ClaimUtility.getOwnerByClaim
```

### 验证claim的颁发者是否正确及状态是否有效
```
ClaimUtility.verifyClaim(String claim, String issuer)
```

### 验证签名
```
ClaimUtility.verifySignature(String ontId, String signedTx)
```