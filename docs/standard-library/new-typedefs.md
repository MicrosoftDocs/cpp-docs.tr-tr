---
title: '&lt;Yeni&gt; tür tanımları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
caps.latest.revision: 7
manager: ghogen
ms.openlocfilehash: 53a13168986171d3240cc15e405fc08b3db07e96
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
