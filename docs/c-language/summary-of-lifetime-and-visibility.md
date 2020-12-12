---
description: 'Daha fazla bilgi edinin: yaşam süresi ve görünürlük Özeti'
title: Ömür ve Görünürlük Özeti
ms.date: 11/04/2016
helpviewer_keywords:
- lifetime, and visibility
- visibility, identifiers
ms.assetid: ea05a253-7658-482c-9a6b-abd71169c42d
ms.openlocfilehash: a1ce139b4fdc2562862eaef1828ec481685eca60
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114487"
---
# <a name="summary-of-lifetime-and-visibility"></a>Ömür ve Görünürlük Özeti

Aşağıdaki tabloda çoğu tanımlayıcı için ömür ve görünürlük özelliklerinin bir özeti verilmiştir. İlk üç sütun, yaşam süresini ve görünürlüğünü tanımlayan özniteliklere sahiptir. İlk üç sütun tarafından verilen özniteliklere sahip bir tanımlayıcı, dördüncü ve beşinci sütunlarda gösterilen ömür ve görünürlüğe sahiptir. Ancak, tablo olası tüm durumları kapsamaz. Daha fazla bilgi için [depolama sınıflarına](../c-language/c-storage-classes.md) bakın.

### <a name="summary-of-lifetime-and-visibility"></a>Ömür ve Görünürlük Özeti

|Öznitelikler:<br /><br /> Level|Öğe|Storage-Class<br /><br /> Belirleyici|Sonuç:<br /><br /> Ömür|Görüş Mesafesi|
|---------------------------|----------|----------------------------------|--------------------------|----------------|
|Dosya kapsamı|Değişken tanımı|**`static`**|Genel|Kaynak dosyanın gerçekleştiği geri kalanı|
||Değişken bildirimi|**`extern`**|Genel|Kaynak dosyanın gerçekleştiği geri kalanı|
||İşlev prototipi veya tanımı|**`static`**|Genel|Tek kaynak dosyası|
||İşlev prototipi|**`extern`**|Genel|Kaynak dosyanın kalanı|
|Blok kapsamı|Değişken bildirimi|**`extern`**|Genel|Blok|
||Değişken tanımı|**`static`**|Genel|Blok|
||Değişken tanımı|**`auto`** veya **`register`**|Yerel|Blok|

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, değişkenlerin blok, iç içe geçme ve görünürlüğünü göstermektedir:

### <a name="code"></a>Kod

```c
// Lifetime_and_Visibility.c

#include <stdio.h>

int i = 1;  // i defined at external level

int main()  // main function defined at external level
{
    printf_s( "%d\n", i ); // Prints 1 (value of external level i)
    {                                 // Begin first nested block
        int i = 2, j = 3;          // i and j defined at internal level
        printf_s( "%d %d\n", i, j );  // Prints 2, 3
        {                             // Begin second nested block
            int i = 0;                // i is redefined
            printf_s( "%d %d\n", i, j ); // Prints 0, 3
        }                             // End of second nested block
        printf_s( "%d\n", i );        // Prints 2 (outer definition
                                      //  restored)
    }                                 // End of first nested block
    printf_s( "%d\n", i );            // Prints 1 (external level
                                      // definition restored)
    return 0;
}
```

### <a name="comments"></a>Yorumlar

Bu örnekte, dört görünürlük düzeyi vardır: dış düzey ve üç blok düzeyi. Değerler her deyimin sonraki açıklamalarda gösterildiği gibi ekrana yazdırılır.

## <a name="see-also"></a>Ayrıca bkz.

[Ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)
