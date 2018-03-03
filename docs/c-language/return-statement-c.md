---
title: "Statement (C) dönüş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ( ) parentheses in return statements
ms.assetid: 18cd82cf-f899-4b28-83ad-4eff353ddcb4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d5ec29b7348d858b502f292efd797020a17bfa0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="return-statement-c"></a>return Deyimi (C)
`return` Deyimi bir işlev yürütülmesi sonlandırır ve denetim çağıran işleve geri döndürür. Çağrının hemen ardından noktada arama işlevinde yürütme sürdürür. A `return` deyimi bir değer de çağıran işleve geri dönebilirsiniz. Bkz: [dönüş türü](../c-language/return-type.md) daha fazla bilgi için.  
  
## <a name="syntax"></a>Sözdizimi  
 *atlama deyimi*:  
 **dönüş***ifade* kabul**;**   
  
 Değeri *ifade*, varsa, çağıran işleve geri döndürülür. Varsa *ifade* olan atlanırsa, işlevin dönüş değeri tanımlanmamış. İfade varsa, değerlendirilir ve işlev tarafından döndürülen tür dönüştürülür. İşlev dönüş türü ile bildirilmedi, `void`, `return` deyimi bir ifade içeren bir uyarı oluşturur ve ifade değerlendirilmez.  
  
 Öyle değilse `return` çağrılan işlev son deyim yürütüldükten sonra deyimi işlev tanımında görünüyor, denetimini otomatik olarak çağıran işleve geri döndürür. Bu durumda, çağrılan işlev dönüş değerini tanımlanmamıştır. Dönüş değeri gerekli değilse işleve sahip bildirme `void` dönüş türü; Aksi takdirde, varsayılan dönüş türü: `int`.  
  
 Birçok Programcı parantez içine kullanmasını *ifade* bağımsız değişkeni `return` deyimi. Ancak, C parantez gerektirmez.  
  
 Bu örnekte gösterilmiştir `return` deyimi:  
  
```  
#include <limits.h>  
#include <stdio.h>  
  
void draw( int i, long long ll );  
long long sq( int s );  
  
int main()  
{  
    long long y;  
    int x = INT_MAX;  
  
    y = sq( x );  
    draw( x, y );  
    return x;  
}  
  
long long sq( int s )  
{  
    // Note that parentheses around the return expression   
    // are allowed but not required here.  
    return( s * (long long)s );  
}  
  
void draw( int i, long long ll )  
{  
    printf( "i = %d, ll = %lld\n", i, ll );  
    return;  
}  
  
```  
  
 Bu örnekte, `main` işlevi iki işlevi çağırır: `sq` ve `draw`. `sq` İşlevi değerini döndürür `x * x` için `main`, dönüş değeri atandığı burada `y`. Dönüş ifadesinde parantezler `sq` ifadenin bir parçası değerlendirilir ve dönüş deyimi tarafından gerekli değildir. Dönüş türüne dönüştürmeden önce dönüş ifadesi değerlendirilir beri `sq` beklenmeyen sonuçlara yol açabilecek bir olası tamsayı taşma önlemek için dönüş türü ile bir cast ifadesi türü zorlar. `draw` İşlevi olarak bildirilen bir `void` işlevi. Bunu parametrelerinin değerlerini yazdırır ve ardından boş return deyiminin işlevi sona erer ve bir değer döndürmüyor. Dönüş değerini atama denemesi `draw` bir tanılama iletisi verilmesine neden olur. `main` İşlevi sonra değerini döndürür `x` işletim sistemi.  
  
 Örnek çıktı şu şekildedir:  
  
```Output  
i = 2147483647, ll = 4611686014132420609  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Deyimler](../c-language/statements-c.md)