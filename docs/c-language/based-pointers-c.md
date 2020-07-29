---
title: Tabanlı İşaretçiler (C)
ms.date: 11/04/2016
helpviewer_keywords:
- __based keyword [C]
- based pointers
- pointers, based
- based addressing
ms.assetid: b5446920-89e0-4e2f-91f3-1f2a769a08e8
ms.openlocfilehash: d1ef1ec98d718e408621f5303e809d09020d5719
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87190253"
---
# <a name="based-pointers-c"></a>Tabanlı İşaretçiler (C)

**Microsoft'a Özgü**

[__based (C++ Başvurusu)](../cpp/based-pointers-cpp.md)

Microsoft 32-bit ve 64-bit C derleyicileri için, temel alınan bir işaretçi, 32-bit veya 64-bit işaretçi tabanından bir 32-bit veya 64-bit denkleştirilir. Tabanlı adresleme, nesnelerin ayrıldığı bölümler üzerinde denetim için yararlıdır, böylece yürütülebilir dosyanın boyutunu azaltır ve yürütme hızını artırır. Genel olarak, bir tabanlı işaretçinin belirtilmesine yönelik form

> *tür* **__based (** *taban* **)** *bildirimci*

"İşaretçi tabanlı" temel adresleme, taban olarak bir işaretçi belirtimini mümkün bir şekilde sunar. Temel işaretçi, temel aldığı işaretçinin başlangıcında başlayan bellek bölümünün bir uzaklığında oluşur. İşaretçi adreslerini temel alan işaretçiler, **`__based`** 32-bit ve 64 bit derlemelerde geçerli olan anahtar sözcüğünün tek biçimidir. Bu tür derlemelerde, 32 bit veya 64 bit, 32-bit veya 64-bit tabanlardır.

İşaretçilere göre işaretçilerin bir kullanımı da, işaretçiler içeren kalıcı tanımlayıcılara yöneliktir. İşaretçiye göre işaretçilerden oluşan bağlantılı bir liste diske kaydedilebilir ve daha sonra işaretçiler geçerli kalacak şekilde bellekte başka bir yere yeniden yüklenebilir.

Aşağıdaki örnek, bir işaretçiye dayalı bir işaretçi gösterir.

```C
void *vpBuffer;

struct llist_t
{
    void __based( vpBuffer ) *vpData;
    struct llist_t __based( vpBuffer ) *llNext;
};
```

`vpBuffer` işaretçisine, programda daha sonra ayrılan belleğin adresi atanır. Bağlantılı liste, `vpBuffer` değerine göre yeniden konumlandırılır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimciler ve değişken bildirimleri](../c-language/declarators-and-variable-declarations.md)
