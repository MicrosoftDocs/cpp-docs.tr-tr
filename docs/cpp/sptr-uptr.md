---
title: __sptr, __uptr | Microsoft Docs
ms.custom: ''
ms.date: 10/10/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __uptr_cpp
- __sptr_cpp
- __uptr
- __sptr
- _uptr
- _sptr
dev_langs:
- C++
helpviewer_keywords:
- __sptr modifier
- __uptr modifier
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa67c815fdfeac0f5728ecd671aaa8f04a59ef89
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163484"
---
# <a name="sptr-uptr"></a>__sptr, __uptr

**Microsoft'a özgü**

Kullanım **__sptr** veya **__uptr** nasıl derleyicinin 64-bit işaretçi bir 32 bit işaretçi dönüştürür belirtmek için bir 32 bit işaretçi bildirimde değiştiricisi. Bir 64-bit işaretçi değişkenine atanan ya da bir 64-bit platformda başvurusu bir 32 bit işaretçi gibi dönüştürülür.

Microsoft belge desteği için 64-bit platformlarda bazen bir 32 bit işaretçi en önemli bite imza biti ifade eder. Varsayılan olarak, derleyici bir 32 bit işaretçi bir 64-bit işaretçiye dönüştürmek için işaret uzantısı kullanır. Diğer bir deyişle, en az önemli 32 bit 64-bit işaretçisinin 32 bit işaretçi değerine ayarlanır ve en önemli 32 bit imza biti 32-bit işaretçinin değerine ayarlanır. Bu dönüştürme, imza biti 0 ise, ancak imza biti 1 değilse, doğru sonuçlar verir. Örneğin, 32-bit adres 0x7FFFFFFF eşdeğer 64 bit adres 0x000000007FFFFFFF verir, ancak 0x80000000 32-bit adres yanlış 0xFFFFFFFF80000000 için değiştirilir.

**__Sptr**, veya işaretçi, imzalanmış değiştiricisi, bir işaretçi dönüştürme 32 bit işaretçi için imza biti bir 64-bit işaretçi en önemli bitlerini ayarlamak belirtir. **__Uptr**, veya işaretsiz işaretçi değiştirici belirtir bir dönüştürme en önemli bitleri sıfır olarak ayarlayın. Aşağıdaki bildirimleri göster **__sptr** ve **__uptr** değiştiriciler, iki nitelenmemiş işaretçiler ile kullanılan iki işaretçi ile tam [__ptr32](../cpp/ptr32-ptr64.md) türünü ve bir işlevi parametre.

```cpp
int * __sptr psp;
int * __uptr pup;
int * __ptr32 __sptr psp32;
int * __ptr32 __uptr pup32;
void MyFunction(char * __uptr __ptr32 myValue);
```

Kullanım **__sptr** ve **__uptr** işaretçi bildirimleri ile değiştiriciler. Konumunu değiştiricilerini kullanmak bir [işaretçi türü niteleyici](../c-language/pointer-declarations.md), değiştirici başka bir deyişle, yıldız işareti izlemeniz gerekir. Değiştiricilerini kullanamazsınız [üye işaretçileri](../cpp/pointers-to-members.md). Değiştiriciler işaretçi olmayan bildirimleri etkilemez.

Önceki sürümlerle uyumluluk için **_sptr** ve **_uptr** için eş anlamlı sözcükler olan **__sptr** ve **__uptr** derleyici seçeneği sürece [/Za \(dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md) belirtilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek kullanan 32 bit işaretçiler bildirir **__sptr** ve **__uptr** değiştiriciler, her 32 bit işaretçi bir 64-bit işaretçi değişkenine atar ve ardından her 64 - onaltılık değeri görüntüler. bit işaretçi. Bu örnek, yerel 64 bit derleyici ile derlenmiş ve 64-bit bir platform üzerinde yürütülür.

```cpp
// sptr_uptr.cpp
// processor: x64
#include "stdio.h"

int main()
{
    void *        __ptr64 p64;
    void *        __ptr32 p32d; //default signed pointer
    void * __sptr __ptr32 p32s; //explicit signed pointer
    void * __uptr __ptr32 p32u; //explicit unsigned pointer

// Set the 32-bit pointers to a value whose sign bit is 1.
    p32d = reinterpret_cast<void *>(0x87654321);
    p32s = p32d;
    p32u = p32d;

// The printf() function automatically displays leading zeroes with each 32-bit pointer. These are unrelated
// to the __sptr and __uptr modifiers.
    printf("Display each 32-bit pointer (as an unsigned 64-bit pointer):\n");
    printf("p32d:       %p\n", p32d);
    printf("p32s:       %p\n", p32s);
    printf("p32u:       %p\n", p32u);

    printf("\nDisplay the 64-bit pointer created from each 32-bit pointer:\n");
    p64 = p32d;
    printf("p32d: p64 = %p\n", p64);
    p64 = p32s;
    printf("p32s: p64 = %p\n", p64);
    p64 = p32u;
    printf("p32u: p64 = %p\n", p64);
    return 0;
}
```

```Output
Display each 32-bit pointer (as an unsigned 64-bit pointer):
p32d:       0000000087654321
p32s:       0000000087654321
p32u:       0000000087654321

Display the 64-bit pointer created from each 32-bit pointer:
p32d: p64 = FFFFFFFF87654321
p32s: p64 = FFFFFFFF87654321
p32u: p64 = 0000000087654321
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft'a Özel Değiştiriciler](../cpp/microsoft-specific-modifiers.md)