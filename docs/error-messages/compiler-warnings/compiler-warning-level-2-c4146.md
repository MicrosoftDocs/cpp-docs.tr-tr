---
title: "Derleyici Uyarısı (Düzey 2) C4146 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4146
dev_langs:
- C++
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7a9a67beb4dc122c25318c1796e22a4c35dbe38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4146"></a>Derleyici Uyarısı (Düzey 2) C4146
birli işleç sonucu hala imzasız imzasız türüne uygulanacağını eksi  
  
 Tekli eksi (değilleme) genellikle bir imzasız türüne uygulandığında anlamsız şekilde imzasız türler yalnızca negatif olmayan değerleri içerebilir. Negatif olmayan işleneni ve sonucu.  
  
 Pratikte, programcı -2147483648 olan en küçük tamsayı değeri express çalışırken bu oluşur. Bu değer ifadesi iki aşamada işlendiğinden -2147483648 yazılamıyor:  
  
1.  Sayı 2147483648 değerlendirilir. 2147483647 en büyük tamsayı değerinden büyük olduğu için 2147483648 türünde değil [int](../../c-language/integer-types.md), ancak `unsigned int`.  
  
2.  Tekli eksi 2147483648 olmasını da yapılır imzasız bir sonuç değeri uygulanır.  
  
 Sonuç imzasız türü beklenmeyen davranışlara neden olabilir. Sonuç bir karşılaştırma kullanılan sonra diğer işleneni olduğunda imzasız karşılaştırma, örneğin, kullanılabilir bir `int`. Bu, aşağıdaki örnek program tek bir satır neden yazdırır açıklanmaktadır.  
  
 Beklenen ikinci satırın `1 is greater than the most negative int`, çünkü yazdırılan değil `((unsigned int)1) > 2147483648` false olur.  
  
 Türüne sahip lımıts.h ınt_mın kullanarak C4146 önleyebilirsiniz **imzalı int**.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4146 oluşturur:  
  
```  
// C4146.cpp  
// compile with: /W2  
#include <stdio.h>  
  
void check(int i)   
{  
    if (i > -2147483648)   // C4146  
        printf_s("%d is greater than the most negative int\n", i);  
}  
  
int main()   
{  
    check(-100);  
    check(1);  
}  
```