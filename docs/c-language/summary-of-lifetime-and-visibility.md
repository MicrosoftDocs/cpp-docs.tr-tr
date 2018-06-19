---
title: Ömür ve görünürlük özeti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lifetime, and visibility
- visibility, identifiers
ms.assetid: ea05a253-7658-482c-9a6b-abd71169c42d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2c8b6f9c6be0b07dba710e50f71f96bdf3f0eb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389786"
---
# <a name="summary-of-lifetime-and-visibility"></a>Ömür ve Görünürlük Özeti
Aşağıdaki tabloda, çoğu tanımlayıcıları ömür ve görünürlük özelliklerini özetidir. İlk üç sütun ömür ve görünürlük tanımlayan öznitelikleri verin. İlk üç sütun tarafından verilen özniteliklere sahip bir tanımlayıcı ömür ve görünürlük dördüncü ve beşinci sütunlarında gösterilen sahiptir. Ancak, tablonun tüm olası durumların kapsamaz. Başvurmak [depolama sınıfları](../c-language/c-storage-classes.md) daha fazla bilgi için.  
  
### <a name="summary-of-lifetime-and-visibility"></a>Ömür ve Görünürlük Özeti  
  
|Öznitelikleri:<br /><br /> Düzey|Öğe|Depolama sınıfı<br /><br /> Belirleyici|Sonuç:<br /><br /> Ömür|Görünürlük|  
|---------------------------|----------|----------------------------------|--------------------------|----------------|  
|Dosya kapsamı|Değişken tanımı|**static**|Global|Kaynak dosya içinde oluştuğu geri kalanı|  
||Değişken bildirimi|`extern`|Global|Kaynak dosya içinde oluştuğu geri kalanı|  
||İşlev prototipi veya tanımı|**static**|Global|Tek kaynak dosyası|  
||İşlev prototipi|`extern`|Global|Kaynak dosyanın kalanını|  
|Blok kapsamı|Değişken bildirimi|`extern`|Global|Blok|  
||Değişken tanımı|**static**|Global|Blok|  
||Değişken tanımı|**Otomatik** veya **kaydetme**|Yerel|Blok|  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, blokları, iç içe geçme ve değişkenleri görünürlüğünü gösterilmektedir:  
  
### <a name="code"></a>Kod  
  
```  
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
  
### <a name="comments"></a>Açıklamalar  
 Bu örnekte, görünürlük dört düzeyi vardır: dış düzeyi ve üç blok düzeyi. Değerlerin her deyiminden açıklamalarda belirtildiği gibi ekranına yazdırılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ömür, Kapsam, Görünürlük ve Bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)