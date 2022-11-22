---
date: 2022-10-17T15:20:00+08:00
draft: false
dropCap: false
summary: 2022年10月16日，阿甘科技的博客开始和世界招手。
tags: ['QuantumultX','阿甘科技的博客']
title: "QuantumultX Template"
tocNum: false
---
```javascript
/*
QX: ^https:\/\/api\.revenuecat\.com\/v1\/subscribers\/ url script-response-body revenuecat.js
hostname = api.revenuecat.com

仅限阿甘科技群组学习交流，严禁外传！

By 阿甘科技

参考Nobyda数据

注意:此脚本仅作模版使用，使用范围有限，能者自用。
*/
let obj=JSON.parse($response.body);
let url=$request.url;

if(url.endsWith("offerings")||url.endsWith("products")) {
	$done({});
} else {
	// Noto笔记Lifetime
	if (url.indexOf("EE5F4363-50A2-4A57-8172-DA69F76DE2FB")!=-1) {
		obj["subscriber"]["entitlements"]["pro"]={
			"expires_date": null,
			"product_identifier": "com.lkzhao.editor.full.deal",
			"purchase_date": "2019-12-01T00:00:00Z"
		};
		obj["subscriber"]["non_subscriptions"]["com.lkzhao.editor.full.deal"]=[{
			"id": "12345qwert",
			"is_sandbox": false,
			"original_purchase_date": "2019-12-01T00:00:00Z",
			"purchase_date": "2019-12-01T00:00:00Z",
			"store": "app_store"
		}];
	}
	// Airmail Premium
	if (url.indexOf("5647911E-B243-48C9-A25C-29116412A20D")!=-1) {
		obj["subscriber"]["entitlements"]={
			"Airmail Premium": {
				"expires_date": "2099-12-01T00:00:00Z",
				"product_identifier": "Airmail_iOS_Yearly",
				"purchase_date": "2019-12-01T00:00:00Z"
			}
		};
		obj["subscriber"]["subscriptions"]={
			"Airmail_iOS_Yearly": {
				"is_sandbox": false,
				"period_type": "active",
				"billing_issues_detected_at": null,
				"unsubscribe_detected_at": null,
				"expires_date": "2099-12-01T00:00:00Z",
				"original_purchase_date": "2019-10-31T00:00:00Z",
				"purchase_date": "2019-10-31T00:00:00Z",
				"store": "app_store"
			}
		};
	}
}

$done({body:JSON.stringify(obj)});
Footer

```

<!--more-->
