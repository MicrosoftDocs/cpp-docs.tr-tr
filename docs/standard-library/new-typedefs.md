---
title: '&lt;Yeni&gt; tür tanımları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 5ab0087a85cb2fce6fa300db136e7c60c66b0b5c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltnewgt-typedefs"></a>&lt;Yeni&gt; tür tanımları

||
|-|
|[new_handler](#new_handler)|

## <a name="new_handler"></a>  new_handler

Uygun bir işlev türü noktasına yeni bir işleyici olarak kullanın.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>Açıklamalar

Bu tür bir işleyici işlevi tarafından çağrılır **operatornew** veya `operator new[]` olduğunda bunlar olamaz karşılamak ek depolama alanı için bir istek.

### <a name="example"></a>Örnek

Bkz: [set_new_handler](../standard-library/new-functions.md#set_new_handler) kullanarak bir örnek için `new_handler` dönüş değeri olarak.

## <a name="see-also"></a>Ayrıca bkz.

[\<Yeni >](../standard-library/new.md)<br/>
