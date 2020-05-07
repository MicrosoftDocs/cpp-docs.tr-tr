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
ms.openlocfilehash: 6bbae7c778f5196ac0dca387265499b27119a367
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233840"
---
# <a name="extern-storage-class-specifier"></a>extern Depolama Sınıfı Tanımlayıcısı

**Extern** depolama sınıfı belirticisiyle belirtilen değişken, başka bir kaynak dosyada tanımlanmış aynı ada sahip bir değişkene başvurudur. Dış düzey değişken tanımını görünür hale getirmek için kullanılır. **Extern** olarak belirtilen bir değişkenin kendisi için ayrılmış depolama alanı yoktur; yalnızca bir addır.

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

Bu örnekte, değişken `i` , 1 başlangıç değeri ile Source1. c içinde tanımlanmıştır. SOURCE2. c içindeki bir **extern** bildirimi, bu dosyada ' ı ' görünür hale getirir.

`func` İşlevinde, genel değişkenin `i` adresi **statik** işaretçi değişkenini `external_i`başlatmak için kullanılır. Bu, genel değişken **statik** yaşam süresine sahip olduğundan ve bu nedenle adresinin programın yürütülmesi sırasında değişmediği anlamına gelir. Sonra, bir değişken `i` ilk değeri 16 olan yerel bir `func` değişken olarak kapsamı içinde tanımlanır. Bu tanım, yerel değişken için adının kullanımıyla gizlenen dış düzeyin `i`değerini etkilemez. Genel `i` değerine artık yalnızca işaretçi `external_i`aracılığıyla erişilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[İç Düzey Bildirimleri Depolama Sınıfı Tanımlayıcıları](../c-language/storage-class-specifiers-for-internal-level-declarations.md)
