---
title: İşlev bildirimlerinin ve tanımlarının kullanılmayan formları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- old style function declarations
ms.assetid: 67c5038f-0529-4f29-9d0f-c27580977b50
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d7bb117ff75ae96c8cfa7041534ed0696ad03e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384287"
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
  
 Bir `int` ile aynı boyutta tamsayı veya işaretçi döndüren işlevlerin (bildirimi önerilse de) bildirime sahip olması gerekli değildir.  
  
 ANSI C standardı ile uyum açısından, üç nokta kullanan eski stil işlev bildirimleri, /Za seçeneğiyle derlerken şimdi bir hata, /Ze ile derlerken ise düzey 4 uyarısı oluşturur. Örneğin:  
  
```  
void funct1( a, ... )  /* Generates a warning under /Ze or */  
int a;                 /* an error when compiling with /Za */  
{  
}  
```  
  
 Bu bildirimi bir prototip olarak yeniden yazmalısınız:  
  
```  
void funct1( int a, ... )  
{  
}  
```  
  
 Eski stil işlev bildirimleri ayrıca, aynı işlevi daha sonra üç nokta ile veya yükseltilen tür ile aynı olmayan bir türden parametre ile bildirdiğinizde veya tanımladığınızda da bir uyarı oluşturur.  
  
 Sonraki bölümde [C işlev tanımları](../c-language/c-function-definitions.md), eski stil söz dizimi de dahil olmak üzere, işlev tanımları için söz dizimi görülmektedir. Eski Tarz sözdiziminde parametrelerin listesi için nonterminal olan *tanımlayıcı listesi*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevlere Genel Bakış](../c-language/overview-of-functions.md)