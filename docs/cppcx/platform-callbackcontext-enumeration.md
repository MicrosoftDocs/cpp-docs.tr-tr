---
title: 'Platform:: CallbackContext numaralandırması'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
ms.openlocfilehash: 1daa3988fcb985dab9d3083233a3703a20cc2fdb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214298"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform:: CallbackContext numaralandırması

Geri çağırma işlevinin (olay işleyicisi) çalıştırıldığı iş parçacığı bağlamını belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
enum class CallbackContext {};
```

### <a name="members"></a>Üyeler

|Tür kodu|Açıklama|
|---------------|-----------------|
|Herhangi biri|Geri çağırma işlevi herhangi bir iş parçacığı bağlamında çalıştırılabilir.|
|Naklettiğiniz|Geri çağırma işlevi, yalnızca zaman uyumsuz işlemi başlatan iş parçacığı bağlamında çalıştırılabilir.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd
