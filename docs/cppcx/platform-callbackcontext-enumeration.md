---
title: Platform::CallbackContext numaralandırması
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
ms.openlocfilehash: 7f4e020ab0b1e377456c27d3b4666e15b5a4f7a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441360"
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