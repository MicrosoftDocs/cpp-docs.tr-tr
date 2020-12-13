---
description: 'Daha fazla bilgi edinin: &lt; bellek &gt; numaralandırmalar'
title: '&lt;bellek &gt; numaralandırmalar'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: da9bb22a6095f74b94e1745210fa55061ecf3c71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149103"
---
# <a name="ltmemorygt-enums"></a>&lt;bellek &gt; numaralandırmalar

## <a name="pointer_safety-enumeration"></a><a name="pointer_safety"></a> pointer_safety numaralandırması

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

`relaxed` --güvenli bir şekilde türetilmeyen işaretçiler (açıkça tanımlanmış veya ayrılmış nesnelere işaretçiler), güvenli şekilde türetilen ile aynı şekilde işlenir.

`preferred` --daha önce olduğu gibi, güvenli bir şekilde türemeyen işaretçiler başvurulmamalıdır.

`strict` --güvenle türemeyen işaretçiler, güvenli bir şekilde türetilenlerden farklı şekilde ele alınabilirler.
