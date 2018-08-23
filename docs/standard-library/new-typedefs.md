---
title: '&lt;Yeni&gt; typedefs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: bbfe7d2c24cb589925c70c70235f6de112d274f1
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42464988"
---
# <a name="ltnewgt-typedefs"></a>&lt;Yeni&gt; tür tanımları

| |
| - |
|[new_handler](#new_handler)|

## <a name="new_handler"></a>  new_handler

Uygun bir işlev türü işaret yeni bir işleyici kullanın.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>Açıklamalar

Bu tür bir işleyici işlevi çağıran **operatornew** veya `operator new[]` ne zaman bunlar olamaz karşılamak için ek depolama alanı istek.

### <a name="example"></a>Örnek

Bkz: [set_new_handler](../standard-library/new-functions.md#set_new_handler) bir örnek için `new_handler` dönüş değeri olarak.

## <a name="see-also"></a>Ayrıca bkz.

[\<Yeni >](../standard-library/new.md)<br/>
