---
title: return deyimi (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- return_cpp
dev_langs:
- C++
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d6857983412b2037b8958c2b1a0bee9d9dda053
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="return-statement-c"></a>return Deyimi (C++)
Bir işlev yürütülmesi sonlandırır ve denetim çağıran işleve döndürür (veya işletim sistemine denetiminden aktarırsanız `main` işlevi). Çağrının hemen ardından noktada arama işlevinde yürütme sürdürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
return [expression];  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `expression` Yan tümcesi varsa, dönüştürülür işlevi bildiriminde belirtilen tür için bir başlatma gerçekleştirilen olur. İfade türü bir dönüştürme `return` işlevinin türü geçici nesneler oluşturabilir. Temporaries ne zaman ve nasıl oluşturulduğu hakkında daha fazla bilgi için bkz: [geçici nesneler](../cpp/temporary-objects.md).  
  
 Değeri `expression` yan tümcesi, çağıran işleve geri döndürülür. İfade atlanırsa, işlevin dönüş değeri tanımlanmamıştır. Oluşturucular ve yok ediciler ve türünün işlevlerinin `void`, bir ifadede belirtemezsiniz `return` deyimi. Tüm diğer türleri işlevlerinin bir ifadede belirtmelisiniz `return` deyimi.  
  
 Denetim akışı işlev tanımı kapsayan blok çıktığında, olduğu gibi aynı sonucudur varsa bir `return` deyimi bir ifade olmadan yürütüldü. Bu değer döndürme olarak bildirilen işlevler için geçersiz.  
  
 Bir işlev herhangi bir sayıda olabilir `return` deyimleri.  
  
 Aşağıdaki örnek bir ifade ile kullanan bir `return` iki tamsayının en büyük elde etmek için bildirimi.  
  
## <a name="example"></a>Örnek  
  
```  
// return_statement2.cpp  
#include <stdio.h>  
  
int max ( int a, int b )  
{  
   return ( a > b ? a : b );  
}  
  
int main()  
{  
    int nOne = 5;  
    int nTwo = 7;  
  
    printf_s("\n%d is bigger\n", max( nOne, nTwo ));  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atlama deyimleri](../cpp/jump-statements-cpp.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)