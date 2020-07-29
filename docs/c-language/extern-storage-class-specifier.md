---
title: extern Depolama Sınıfı Tanımlayıcısı
ms.date: 07/10/2018
helpviewer_keywords:
- extern keyword [C]
- storage class specifiers, extern
- extern keyword [C], storage class specifier
- external linkage, storage-class specifiers
- external linkage, extern modifier
ms.assetid: 6e16d927-291f-49e4-986c-9d91a482a441
ms.openlocfilehash: e3242f86e30dcf3227586400b83266ad366ec7e8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217109"
---
# <a name="extern-storage-class-specifier"></a>extern Depolama Sınıfı Tanımlayıcısı

**`extern`** Depolama sınıfı belirticisiyle belirtilen değişken, başka bir kaynak dosyada tanımlanmış aynı ada sahip bir değişkene başvurudur. Dış düzey değişken tanımını görünür hale getirmek için kullanılır. Olarak belirtilen bir değişkenin **`extern`** kendisi için ayrılmış depolama alanı yoktur; yalnızca bir addır.

## <a name="example"></a>Örnek

Bu örnekte, iç ve dış düzeyi bildirimler gösterilmektedir:

```c

// Source1.c

int i = 1;

// Source2. c

#include <stdio.h>

// Refers to the i that is defined in Source1.c:
extern int i;

void func(void);

int main()
{
    // Prints 1:
    printf_s("%d\n", i);
    func();
    return;
}

void func(void)
{
    // Address of global i assigned to pointer variable:
    static int *external_i = &i;

    // This definition of i hides the global i in Source.c:
    int i = 16;

    // Prints 16, 1:
    printf_s("%d\n%d\n", i, *external_i);
}
```

Bu örnekte, değişken, `i` 1 başlangıç değeri Ile Source1. c içinde tanımlanmıştır. **`extern`** Source2. c içindeki bir bildirim, bu dosyada ' ı ' görünür hale getirir.

`func`İşlevinde, genel değişkenin adresi, `i` işaretçi değişkenini başlatmak için kullanılır **`static`** `external_i` . Bu, genel değişkenin ömrü sona uğradığından **`static`** , yani adresinin programın yürütülmesi sırasında değişmediği anlamına gelir. Sonra, bir değişken `i` `func` ilk değeri 16 olan yerel bir değişken olarak kapsamı içinde tanımlanır. Bu tanım, `i` yerel değişken için adının kullanımıyla gizlenen dış düzeyin değerini etkilemez. Genel değerine `i` artık yalnızca işaretçi aracılığıyla erişilebilir `external_i` .

## <a name="see-also"></a>Ayrıca bkz.

[Iç düzey bildirimler için depolama sınıfı belirticileri](../c-language/storage-class-specifiers-for-internal-level-declarations.md)
