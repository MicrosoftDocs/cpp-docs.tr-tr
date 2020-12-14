---
description: 'Daha fazla bilgi edinin: Işlev bildirimlerinin ve tanımlarının kullanılmayan formları'
title: İşlev Bildirimlerinin ve Tanımlarının Kullanılmayan Formları
ms.date: 11/04/2016
helpviewer_keywords:
- old style function declarations
ms.assetid: 67c5038f-0529-4f29-9d0f-c27580977b50
ms.openlocfilehash: 7cd66ba1600d4a5fd381819f4b1d3f0beeb30f0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256919"
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

ANSI C standardı ile uyum açısından, üç nokta kullanan eski stil işlev bildirimleri, /Za seçeneğiyle derlerken şimdi bir hata, /Ze ile derlerken ise düzey 4 uyarısı oluşturur. Örneğin:

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
