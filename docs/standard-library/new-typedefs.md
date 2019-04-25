---
title: '&lt;Yeni&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 85c8d0c2974f734783e3d9c2ad1269f84d605dec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223642"
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
