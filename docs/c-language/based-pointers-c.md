---
title: Tabanlı İşaretçiler (C)
ms.date: 11/04/2016
helpviewer_keywords:
- __based keyword [C]
- based pointers
- pointers, based
- based addressing
ms.assetid: b5446920-89e0-4e2f-91f3-1f2a769a08e8
ms.openlocfilehash: e5d8c529adfb92c9db1fdcc5a38f688853606d5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327437"
---
# <a name="based-pointers-c"></a>Tabanlı İşaretçiler (C)

**Microsoft'a Özgü**

[__based (C++ Başvurusu)](../cpp/based-pointers-cpp.md)

Microsoft 32-bit ve 64-bit C derleyicileri için, temel alınan bir işaretçi, 32-bit veya 64-bit işaretçi tabanından bir 32-bit veya 64-bit denkleştirilir. Tabanlı adresleme, nesnelerin ayrıldığı bölümler üzerinde denetim için yararlıdır, böylece yürütülebilir dosyanın boyutunu azaltır ve yürütme hızını artırır. Genel olarak, bir tabanlı işaretçinin belirtilmesine yönelik form

> *tür* **__based (** *taban* **)** *bildirimci*

"İşaretçi tabanlı" temel adresleme, taban olarak bir işaretçi belirtimini mümkün bir şekilde sunar. Temel işaretçi, temel aldığı işaretçinin başlangıcında başlayan bellek bölümünün bir uzaklığında oluşur. İşaretçi adreslerini temel alan işaretçiler, 32-bit ve 64 `__based` bit derlemelerde geçerli olan anahtar sözcüğünün tek biçimidir. Bu tür derlemelerde, 32 bit veya 64 bit, 32-bit veya 64-bit tabanlardır.

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

[Bildirimler ve Değişken Bildirimleri](../c-language/declarators-and-variable-declarations.md)
