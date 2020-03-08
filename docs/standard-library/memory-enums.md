---
title: '&lt;belleği&gt; numaralandırmalar'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 78cdb0fe6c0d9487500804d21fe4ad4870fcad0f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78884084"
---
# <a name="ltmemorygt-enums"></a>&lt;belleği&gt; numaralandırmalar

## <a name="pointer_safety"></a>pointer_safety numaralandırması

`get_pointer_safety`tarafından döndürülen olası değerlerin numaralandırması.

```cpp
class pointer_safety {
   relaxed,
   preferred,
   strict
};
```

### <a name="remarks"></a>Açıklamalar

Kapsamlı **numaralandırma** , `get_pointer_safety()`tarafından döndürülebilecek değerleri tanımlar:

`relaxed`--güvenli bir şekilde türetilmeyen işaretçiler (açıkça tanımlanmış veya ayrılmış nesnelere işaretçiler), güvenli şekilde türetilen ile aynı şekilde değerlendirilir.

`preferred`--daha önce olduğu gibi, güvenli bir şekilde türemeyen işaretçiler başvurulmamalıdır.

`strict`--güvenle türemeyen işaretçiler, güvenli bir şekilde türetilenlerden farklı şekilde ele alınabilirler.
