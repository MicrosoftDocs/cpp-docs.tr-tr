---
description: 'Hakkında daha fazla bilgi edinin: __sptr __uptr'
title: __sptr, __uptr
ms.date: 10/10/2018
f1_keywords:
- __uptr_cpp
- __sptr_cpp
- __uptr
- __sptr
- _uptr
- _sptr
helpviewer_keywords:
- __sptr modifier
- __uptr modifier
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
ms.openlocfilehash: 13e365e0e8258c1860df2f107a3dad0ade76e529
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113733"
---
# <a name="__sptr-__uptr"></a>__sptr, __uptr

**Microsoft'a Özgü**

**`__sptr`** **`__uptr`** Derleyicinin 32 bit işaretçisini 64-bit işaretçisine nasıl dönüştüreceğini belirtmek için 32 bitlik bir işaretçi bildiriminde veya değiştiricisini kullanın. 32 bitlik bir işaretçi dönüştürülür, örneğin, 64 bit işaretçi değişkenine atandığında veya bir 64-bit platformunda başvurulduğunu.

64 bitlik platformları desteklemek için Microsoft belgeleri bazen, işaret biti olarak 32 bitlik bir işaretçinin en önemli bitini ifade eder. Varsayılan olarak, derleyici 32 bitlik bir işaretçiyi 64 bitlik bir işaretçiye dönüştürmek için imza uzantısını kullanır. Diğer bir deyişle, 64 bit işaretçisinin en az önemli 32 biti, 32 bit işaretçisinin değerine ayarlanır ve en önemli 32 bitleri, 32-bit işaretçisinin işaret bitinin değerine ayarlanır. Bu dönüştürme, işaret biti 0 ise ve işaret biti 1 ise doğru sonuçları verir. Örneğin, 32 bitlik adres, 0x000000007FFFFFFF ile eşdeğer 64 bit adresini verir, ancak 32 bit adresi 0x80000000, yanlışlıkla 0xFFFFFFFF80000000 olarak değiştirilmiştir.

**`__sptr`** Veya imzalı işaretçide, değiştirici, bir işaretçi dönüştürmenin 64 bitlik bir işaretçinin en önemli bitlerini 32 bit işaretçisinin işaret bitini ayarlayamadığını belirtir. **`__uptr`** Ya da imzasız işaretçi, değiştirici bir dönüştürmenin en önemli bitleri sıfıra ayarlandığını belirtir. Aşağıdaki bildirimlerde, **`__sptr`** **`__uptr`** iki nitelenmemiş işaretçiyle kullanılan ve değiştiriciler, [__ptr32](../cpp/ptr32-ptr64.md) türü ile nitelenmiş iki işaretçi ve bir işlev parametresi gösterilmektedir.

```cpp
int * __sptr psp;
int * __uptr pup;
int * __ptr32 __sptr psp32;
int * __ptr32 __uptr pup32;
void MyFunction(char * __uptr __ptr32 myValue);
```

**`__sptr`** **`__uptr`** İşaretçi bildirimleri ile ve değiştiricilerini kullanın. Bir [işaretçi türü niteleyicisi](../c-language/pointer-declarations.md)konumundaki değiştiricilerini kullanın, yani değiştiricinin yıldız işaretini izlemesi gerekir. Değiştiriciler [üye işaretçilerle](../cpp/pointers-to-members.md)birlikte kullanılamaz. Değiştiriciler işaretçi olmayan bildirimleri etkilemez.

Önceki sürümlerle uyumluluk için, **_sptr** ve **_uptr** , için eş anlamlılardır **`__sptr`** ve **`__uptr`** [/za \( Disable dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) gibi derleyici seçeneği belirtilmiştir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, ve değiştiricilerini kullanan 32 bitlik işaretçileri bildirir **`__sptr`** **`__uptr`** , her 32 bit işaretçiyi bir 64-bit işaretçi değişkenine atar ve ardından her bir 64-bit işaretçisinin onaltılık değerini görüntüler. Örnek, yerel 64 bit derleyicisi ile derlenir ve 64 bit platformda yürütülür.

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md)
