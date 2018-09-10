---
title: Platform::CallbackContext numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe988a7dee7fb358d9454c06811d7baf2cd4ace0
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101969"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext numaralandırması

Bir geri çağırma işlevi (olay işleyicisi) yürütür iş parçacığı bağlamını belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
enum class CallbackContext {};
```

### <a name="members"></a>Üyeler

|Türü kodu|Açıklama|
|---------------|-----------------|
|Tüm|Geri çağırma işlevi, her iş parçacığı bağlam üzerinde çalıştırabilirsiniz.|
|Aynı|Zaman uyumsuz işlem başlatılan iş parçacığı bağlamı geri çağırma işlevi yürütebilir.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** platformu

**Meta veri:** platform.winmd