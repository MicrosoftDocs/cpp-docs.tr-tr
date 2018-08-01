---
title: for deyimi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: feb14056e3054cdf0e802b16ce9ff20f67da43fe
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401580"
---
# <a name="for-statement-c"></a>for Deyimi (C++)
Koşul yanlış olana kadar sürekli olarak bir deyimi yürütür. Range-based for deyimi hakkında daha fazla bilgi için bkz: [aralık tabanlı for deyimi (C++)](../cpp/range-based-for-statement-cpp.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım **için** belirtilen sayıda yürütülmesi gereken döngüler oluşturmak için.  
  
 **İçin** deyim, aşağıdaki tabloda gösterildiği gibi üç isteğe bağlı bölümden oluşur.  
  
### <a name="for-loop-elements"></a>Döngü Öğeleri için  
  
|Söz Dizimi Adı|Yürütüldüğünde|Açıklama|  
|-----------------|-------------------|-----------------|  
|`init-expression`|Diğer bir öğesinden önce **için** deyimi `init-expression` yalnızca bir kez yürütülür. Denetleyin ardından pasoları `cond-expression`.|Döngü dizinlerini başlatmak için sık kullanılır. Deyimler ya da bildirimler içerebilir.|  
|`cond-expression`|Yürütme, her yinelemesinin yürütülmesinden önce `statement`, ilk yineleme dahil. `statement` yalnızca yürütülen `cond-expression` true (sıfırdan farklı) olarak değerlendirir.|Tamsayı türüne benzersiz bir dönüştürmesi olan bir integral türünü ya da sınıf türünü değerlendiren deyimdir. Genellikle döngü sonlandırma ölçütünü sınamak için kullanılır.|  
|`loop-expression`|Her bir yinelemesini sonunda `statement`. Sonra `loop-expression` yürütüldüğünde, `cond-expression` değerlendirilir.|Genellikle döngü dizinlerini artırmak için kullanılır.|  
  
 Aşağıdaki örnekler farklı kullanım yollarını **için** deyimi.  
  
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
  
 `init-expression` ve `loop-expression` virgülle ayırarak birden çok deyim içerebilir. Örneğin:  
  
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
  
 `loop-expression` Artımlı azaltılabilir veya farklı yollarla değiştirilebilir olabilir.  
  
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
  
 A **için** döngüyü sonlandırır bir [sonu](../cpp/break-statement-cpp.md), [dönüş](../cpp/return-statement-cpp.md), veya [goto](../cpp/goto-statement-cpp.md) (dışında etiketli deyime **için**döngü) içinde `statement` yürütülür. A [devam](../cpp/continue-statement-cpp.md) deyiminde bir **için** döngü yalnızca geçerli yinelemeyi sonlandırır.  
  
 Varsa `cond-expression` olan atlanırsa, true olarak kabul edilir ve **için** olmadan döngü sonlandırılmayacak bir **sonu**, **dönüş**, veya **goto** içinde `statement`.  
  
 Ancak üç alanı **için** deyimi normalde başlatma, sonlandırma için test etmek için kullanılır ve artan, bunlar bu değildir. Örneğin, aşağıdaki kod numaraları 0 ile 4 arasında yazdırır. Bu durumda, `statement` null hesap deyimidir:  
  
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
 C++ standart, içinde bildirilen bir değişkenin belirten bir **için** döngü Git kapsam dışına **için** döngü sona erer. Örneğin:  
  
```cpp  
for (int i = 0 ; i < 5 ; i++) {  
   // do something  
}  
// i is now out of scope under /Za or /Zc:forScope  
```  
  
 Varsayılan olarak, altında [/Ze](../build/reference/za-ze-disable-language-extensions.md), içinde bildirilen bir değişken bir **için** döngü kadar kapsam içinde kalır **için** döngüsünün kapsayan kapsamı sona erer.  
  
 [/ ZC: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) for döngüleri belirtilmesine gerek olmadan bildirilen değişkenlerin standart davranışını etkinleştirir `/Za`.  
  
 Kapsam farklarını kullanmak da mümkündür **için** variables yeniden bildirmek için döngü `/Ze` gibi:  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 Bu standart içinde bildirilen bir değişken davranışını daha yakından taklit eden bir **için** döngüsü içinde bildirilmiş değişkenlerin gerektiren bir **için** döngü döngü bittikten sonra kapsam dışına çıkmaz. Ne zaman bir değişken içinde bildirilmiş bir **için** döngü, derleyici dahili olarak yükseltir, yerel değişkene **için** döngüsünün kapsayan kapsamı olsa bile zaten aynı ada sahip bir yerel değişken.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Yineleme deyimleri](../cpp/iteration-statements-cpp.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [while deyimi (C++)](../cpp/while-statement-cpp.md)   
 [yapın-while deyimi (C++)](../cpp/do-while-statement-cpp.md)   
 [Range-based for Deyimi (C++)](../cpp/range-based-for-statement-cpp.md)