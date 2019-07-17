---
title: '&lt;bellek&gt; sabit listeleri'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: b2f5b50dc1344b95e88742d346e32fc55f821336
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243844"
---
# <a name="ltmemorygt-enums"></a>&lt;bellek&gt; sabit listeleri

## <a name="pointer_safety"></a> pointer_safety numaralandırması

Olası değerler tarafından döndürülen sabit `get_pointer_safety`.

```
class pointer_safety {
   relaxed,
   preferred,
   strict
};
```

### <a name="remarks"></a>Açıklamalar

Kapsamlı **enum** tarafından döndürülen değerleri tanımlar `get_pointer_safety()`:

`relaxed` --olmayan güvenli bir şekilde türetilen işaretçileri (açıkça bildirilen veya ayrılmış nesnelerine işaretçiler) kabul edilir bu güvenli bir şekilde türetilen olarak aynı.

`preferred` --önceden olduğu gibi ancak olmayan güvenli bir şekilde türetilen işaretçileri değil başvurusu.

`strict` --olmayan güvenli bir şekilde türetilen işaretçileri kabul bu güvenli bir şekilde türetilen değerinden farklı.
