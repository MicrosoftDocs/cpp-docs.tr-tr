---
title: '&lt;bellek &gt; numaralandırmalar'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 507628628fcf8bbf8993ce5beb1e02c28ff82147
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222257"
---
# <a name="ltmemorygt-enums"></a>&lt;bellek &gt; numaralandırmalar

## <a name="pointer_safety-enumeration"></a><a name="pointer_safety"></a>pointer_safety numaralandırması

Tarafından döndürülen olası değerlerin numaralandırması `get_pointer_safety` .

```cpp
class pointer_safety {
   relaxed,
   preferred,
   strict
};
```

### <a name="remarks"></a>Açıklamalar

Kapsamlı **`enum`** olarak döndürülebilecek değerleri tanımlar `get_pointer_safety()` :

`relaxed`--güvenli bir şekilde türetilmeyen işaretçiler (açıkça tanımlanmış veya ayrılmış nesnelere işaretçiler), güvenli şekilde türetilen ile aynı şekilde işlenir.

`preferred`--daha önce olduğu gibi, güvenli bir şekilde türemeyen işaretçiler başvurulmamalıdır.

`strict`--güvenle türemeyen işaretçiler, güvenli bir şekilde türetilenlerden farklı şekilde ele alınabilirler.
