---
title: İşlev Bildirimlerinin ve Tanımlarının Kullanılmayan Formları
ms.date: 11/04/2016
helpviewer_keywords:
- old style function declarations
ms.assetid: 67c5038f-0529-4f29-9d0f-c27580977b50
ms.openlocfilehash: 3311fc846ad0f4f80c2e3b61508edd626a13fbb2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218799"
---
# <a name="obsolete-forms-of-function-declarations-and-definitions"></a>İşlev Bildirimlerinin ve Tanımlarının Kullanılmayan Formları

Eski stil işlev bildirimlerinde ve tanımlarında parametreleri bildirmek için, ANSI C standardına göre önerilen sözdiziminden biraz daha farklı kurallar kullanılır. İlk olarak, eski stil bildirimlerde parametre listesi yoktur. İkinci olarak, işlev tanımında parametreler listelenir, ancak türleri parametre listesinde bildirilmez. tür bildirimleri, işlev gövdesini oluşturan bileşik deyimden önce gelir. Eski stil sözdizimi eskimiştir ve yeni kodlarda kullanılmamalıdır. Ancak eski stil sözdizimini kullanan kodlar hala desteklenmektedir. Bu örnekte, bildirimlerin ve tanımların eski formları gösterilmektedir:

```
double old_style();           /* Obsolete function declaration */

double alt_style( a , real )  /* Obsolete function definition */
    double *real;
    int a;
{
    return ( *real + a ) ;
}
```

Bildirim önerilse de, bir tam sayı veya aynı boyuta sahip bir işaretçi döndüren işlevlerin **`int`** bildirime sahip olması gerekmez.

ANSI C standardı ile uyum açısından, üç nokta kullanan eski stil işlev bildirimleri, /Za seçeneğiyle derlerken şimdi bir hata, /Ze ile derlerken ise düzey 4 uyarısı oluşturur. Örnek:

```cpp
void funct1( a, ... )  /* Generates a warning under /Ze or */
int a;                 /* an error when compiling with /Za */
{
}
```

Bu bildirimi bir prototip olarak yeniden yazmalısınız:

```cpp
void funct1( int a, ... )
{
}
```

Eski stil işlev bildirimleri ayrıca, aynı işlevi daha sonra üç nokta ile veya yükseltilen tür ile aynı olmayan bir türden parametre ile bildirdiğinizde veya tanımladığınızda da bir uyarı oluşturur.

Sonraki bölüm olan [C Işlevi tanımları](../c-language/c-function-definitions.md), eski stil sözdizimi dahil olmak üzere işlev tanımlarının sözdizimini gösterir. Eski stil sözdiziminde parametre listesi için Terminal olmayan bir *kimlik listesi*.

## <a name="see-also"></a>Ayrıca bkz.

[IŞLEVLERE genel bakış](../c-language/overview-of-functions.md)
