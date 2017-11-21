---
title: "Kayan nokta sayıları duyarlık kaybedebileceği neden | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ad6d78b6209b2a2d45f0d0e5874dff1271da880b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Kayan Noktalı Sayıların Neden Duyarlık Kaybedebileceği
Kayan noktalı ondalık değer tam bir ikili temsili genellikle gerekmez. Bir yan etkisi, CPU kayan nokta verisi nasıl temsil ettiğini budur. Bu nedenle, bazı duyarlık kaybına karşılaşabilirsiniz ve bazı kayan nokta işlemleri beklenmeyen sonuçlara neden olabilir.  
  
 Bu davranış aşağıdakilerden birini sonucudur:  
  
-   Ondalık sayı ikili gösterimidir kesin olmayabilir.  
  
-   Kullanılan sayılar arasında (örneğin, karıştırma float ve double) tür uyuşmazlığı var.  
  
 Davranışı çözümlemek için çoğu programcıları ya da değer büyüktür veya daha düşük gerekli olduğundan emin olun veya alın ve duyarlık tutacağı bir ikili kodlanmış ondalık (BCD) kitaplığını kullanın.  
  
 Kayan nokta değerlerine ikili gösterimidir duyarlık ve kayan nokta hesaplamaları doğruluğunu etkiler. Microsoft Visual C++ kullanan [IEEE kayan nokta biçimi](../../build/reference/ieee-floating-point-representation.md).  
  
## <a name="example"></a>Örnek  
  
```  
// Floating-point_number_precision.c  
// Compile options needed: none. Value of c is printed with a decimal   
// point precision of 10 and 6 (printf rounded value by default) to   
// show the difference  
#include <stdio.h>  
  
#define EPSILON 0.0001   // Define your own tolerance  
#define FLOAT_EQ(x,v) (((v - EPSILON) < x) && (x <( v + EPSILON)))  
  
int main() {  
   float a, b, c;  
  
   a = 1.345f;  
   b = 1.123f;  
   c = a + b;  
   // if (FLOAT_EQ(c, 2.468)) // Remove comment for correct result  
   if (c == 2.468)            // Comment this line for correct result  
      printf_s("They are equal.\n");  
   else  
      printf_s("They are not equal! The value of c is %13.10f "  
                "or %f",c,c);  
}  
```  
  
```Output  
They are not equal! The value of c is  2.4679999352 or 2.468000  
```  
  
## <a name="comments"></a>Açıklamalar  
 EPSILON için float 1.192092896e olarak için tanımlanan flt_epsılon sabitleri kullanabilirsiniz-07F, ya da çift 2.2204460492503131e olarak için tanımlanan dbl_epsılon-016. Bu sabitleri float.h eklemeniz gerekir. Bu sabit değerler tanımlanmadı en küçük pozitif sayı x, bu tür bu x + 1.0 1.0 eşit değil. Bu çok küçük bir sayı olduğundan, kullanıcı tanımlı dayanıklılık çok büyük sayılar içeren hesaplamalar için içermelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodunuzu iyileştirme](../../build/reference/optimizing-your-code.md)