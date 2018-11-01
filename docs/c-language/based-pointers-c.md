---
title: Tabanlı İşaretçiler (C)
ms.date: 11/04/2016
helpviewer_keywords:
- __based keyword [C]
- based pointers
- pointers, based
- based addressing
ms.assetid: b5446920-89e0-4e2f-91f3-1f2a769a08e8
ms.openlocfilehash: 7d41d1b7a4d19a7837f5aac1eb7975d6cec8c979
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581460"
---
# <a name="based-pointers-c"></a>Tabanlı İşaretçiler (C)

**Microsoft'a özgü**

[__based (C++ Başvurusu)](../cpp/based-pointers-cpp.md)

Microsoft 32-bit ve 64-bit C Derleyicileri için temel alınan bir işaretçinin bir 32 bit veya 64-bit uzaklığı bir 32 bit veya 64-bit işaretçi temeline ' dir. Tabanlı adresleme nesnelerin ayrıldığı bölümleri üzerinde denetim denemek, böylece yürütülebilir dosyanın boyutunu küçültme ve yürütme hızını artırmak için kullanışlıdır. Genel olarak, temel alınan bir işaretçinin belirtmek için formun olduğu

> *tür* **__based (** *temel* **)** *bildirimcisi*

Tabanlı adresleme "işaretçi göre" değişken temel olarak belirtimi bir işaretçi sağlar. Temel, daha sonra temel işaretçisinin başında başlayarak bellek bölümüne bir uzaklık işaretçisidir. İşaretçi adreslerine göre işaretçiler, yalnızca kuralar `__based` 32-bit ve 64 bit derlemelerde geçerli anahtar sözcüğü. Bu tür derlemelerde 32 bit veya 64 bit yapı yer değiştirmelerini bırak bir 32 bit veya 64-bit tabanından değildirler.

İşaretçilere göre işaretçilerin bir kullanımı da, işaretçiler içeren kalıcı tanımlayıcılara yöneliktir. İşaretçiye göre işaretçilerden oluşan bağlantılı bir liste diske kaydedilebilir ve daha sonra işaretçiler geçerli kalacak şekilde bellekte başka bir yere yeniden yüklenebilir.

Aşağıdaki örnek, bir işaretçi bir işaretçiye göre gösterir.

```C
void *vpBuffer;

struct llist_t
{
    void __based( vpBuffer ) *vpData;
    struct llist_t __based( vpBuffer ) *llNext;
};
```

`vpBuffer` işaretçisine, programda daha sonra ayrılan belleğin adresi atanır. Bağlantılı liste, `vpBuffer` değerine göre yeniden konumlandırılır.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)