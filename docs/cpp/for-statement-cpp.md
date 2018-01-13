---
title: for deyimi (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8358af0cd6784b1974767456602350a8ccf1c57f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="for-statement-c"></a>for Deyimi (C++)
Koşul yanlış olana kadar sürekli olarak bir deyimi yürütür. Aralık-based for deyimi hakkında daha fazla bilgi için bkz: [aralık tabanlı için deyimi (C++)](../cpp/range-based-for-statement-cpp.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `for` belirtilen sayıda yürütülmesi gerekir döngüler oluşturmak için ifade.  
  
 `for` Deyimi aşağıdaki tabloda gösterildiği gibi üç isteğe bağlı bölümden oluşur.  
  
### <a name="for-loop-elements"></a>Döngü Öğeleri için  
  
|Söz Dizimi Adı|Yürütüldüğünde|Açıklama|  
|-----------------|-------------------|-----------------|  
|`init-expression`|Başka bir öğenin önce **için** deyimi, `init-expression` yalnızca bir kez çalıştırılır. Denetim sonra geçer `cond-expression`.|Döngü dizinlerini başlatmak için sık kullanılır. Deyimler ya da bildirimler içerebilir.|  
|`cond-expression`|Her yinelemesinden yürütülmesi önce `statement`, ilk yinelemeyi dahil olmak üzere. `statement`yalnızca yürütülen `cond-expression` (sıfır) true olarak değerlendirilir.|Tamsayı türüne benzersiz bir dönüştürmesi olan bir integral türünü ya da sınıf türünü değerlendiren deyimdir. Genellikle döngü sonlandırma ölçütünü sınamak için kullanılır.|  
|`loop-expression`|Her yinelemesinden sonunda `statement`. Sonra `loop-expression` yürütüldüğünde, `cond-expression` değerlendirilir.|Genellikle döngü dizinlerini artırmak için kullanılır.|  
  
 Aşağıdaki örnekler kullanmak için farklı yollar `for` deyimi.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    // The counter variable can be declared in the init-expression.  
    for (int i = 0; i < 2; i++ ){   
       cout << i;  
    }  
    // Output: 01  
    // The counter variable can be declared outside the for loop.  
    int i;  
    for (i = 0; i < 2; i++){  
        cout << i;  
    }  
    // Output: 01  
    // These for loops are the equivalent of a while loop.  
    i = 0;  
    while (i < 2){  
        cout << i++;  
    }  
}  
    // Output: 012  
```  
  
 `init-expression`ve `loop-expression` virgülle ayırarak birden çok deyime içerebilir. Örneğin:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
    int i, j;  
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {  
        cout << "i + j = " << (i + j) << '\n';  
    }  
}  
    // Output:  
    i + j = 15  
    i + j = 17  
    i + j = 19  
```  
  
 `loop-expression`artan veya indirildiği veya diğer yollarla değiştirilmiş olabilir.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
for (int i = 10; i > 0; i--) {  
        cout << i << ' ';  
    }  
    // Output: 10 9 8 7 6 5 4 3 2 1  
    for (int i = 10; i < 20; i = i+2) {  
        cout << i << ' ';  
    }  
    // Output: 10 12 14 16 18  
```  
  
 A `for` döngü sonlandırır bir [sonu](../cpp/break-statement-cpp.md), [dönmek](../cpp/return-statement-cpp.md), veya [goto](../cpp/goto-statement-cpp.md) (etiketli deyimi dışında **için** döngü) içinde `statement` yürütülür. A [devam](../cpp/continue-statement-cpp.md) deyiminde bir `for` döngü yalnızca geçerli yinelemeye sonlandırır.  
  
 Varsa `cond-expression` olan atlanırsa, true olarak değerlendirilir ve **için** olmadan döngü sonlandırılmayacak bir `break`, `return`, veya `goto` içinde `statement`.  
  
 Ancak üç alanlarını `for` deyimi başlatma, sonlandırma için test etme için normal olarak kullanılır ve artan, bunlar bu kullanımları sınırlı değildir. Örneğin, aşağıdaki kod numaraları 0 ile 4 arasında yazdırır. Bu durumda, `statement` null ifadesi:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    int i;  
    for( i = 0; i < 5; cout << i << '\n', i++){  
        ;  
    }  
}  
```  
  
## <a name="for-loops-and-the-c-standard"></a>Döngüler ve C++ Standartı için  
 C++ standart bir değişken bildirilen olduğunu bildiren bir `for` döngü Git sonra kapsam dışında `for` döngü sona erer. Örneğin:  
  
```cpp  
for (int i = 0 ; i < 5 ; i++) {  
   // do something  
}  
// i is now out of scope under /Za or /Zc:forScope  
```  
  
 Varsayılan olarak, altında [/Ze](../build/reference/za-ze-disable-language-extensions.md), bildirilen bir değişken bir `for` döngü kalır kadar kapsamdaki `for` döngü kapsam uçları kapsayan.  
  
 [/ ZC: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) for döngüleri /Za belirtmek zorunda kalmadan bildirilen değişkenlerin standart davranışını etkinleştirir.  
  
 Kapsam farklarının kullanmak da mümkündür `for` değişkenleri /Ze altında aşağıdaki gibi redeclare döngü:  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 Bu daha yakından bildirilen bir değişken standart davranışını taklit eden bir `for` içinde bildirilen değişkenlerin gerektirir döngü bir `for` döngü yapıldıktan sonra kapsamının dışına gitmek için döngü. Ne zaman bir değişken içinde bildirilen bir `for` döngü, derleyici dahili olarak yükseltir, yerel bir değişkene `for` döngü olsa bile zaten aynı ada sahip yerel bir değişken kapsamı kapsayan.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yineleme deyimleri](../cpp/iteration-statements-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [while deyimi (C++)](../cpp/while-statement-cpp.md)   
 [yapın-while deyimi (C++)](../cpp/do-while-statement-cpp.md)   
 [Range-based for Deyimi (C++)](../cpp/range-based-for-statement-cpp.md)