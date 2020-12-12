---
description: 'Daha fazla bilgi edinin: Platform:: CallbackContext numaralandırması'
title: Platform::CallbackContext Numaralandırması
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
ms.openlocfilehash: 36c30b674065f42f7d50a403d1506344ffcfecac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170977"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext Numaralandırması

Geri çağırma işlevinin (olay işleyicisi) çalıştırıldığı iş parçacığı bağlamını belirtir.

## <a name="syntax"></a>Syntax

```cpp
enum class CallbackContext {};
```

### <a name="members"></a>Üyeler

|Tür kodu|Açıklama|
|---------------|-----------------|
|Herhangi bir|Geri çağırma işlevi herhangi bir iş parçacığı bağlamında çalıştırılabilir.|
|Aynı|Geri çağırma işlevi, yalnızca zaman uyumsuz işlemi başlatan iş parçacığı bağlamında çalıştırılabilir.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd
