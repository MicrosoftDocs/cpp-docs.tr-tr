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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161686"
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

**En düşük desteklenen istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** Platform

**Meta veri:** platform.winmd