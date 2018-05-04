---
title: 'Önek arttırma ve azaltma işleçleri: ++ ve--| Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- --
- ++
dev_langs:
- C++
helpviewer_keywords:
- increment operators [C++], syntax
- ++ operator [C++], prefix increment operators
- operators [C++], decrement
- -- operator [C++], prefix decrement operators [C++]
- operators [C++], increment
- decrement operators [C++], syntax
- decrement operators [C++]
ms.assetid: 45ea7fc7-f279-4be9-a216-1d9a0ef9eb7b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 071f21080bd093e5cb299471c8de7009741482f6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="prefix-increment-and-decrement-operators--and---"></a>Önek Arttırma ve Azaltma İşleçleri: ++ ve --
## <a name="syntax"></a>Sözdizimi  
  
```  
++ unary-expression  
-- unary-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Önek arttırma işleci (`++`), işlenen; birine ekler artırılır bu değer ifadesi sonucudur. İşlenen türü bir l-değeri olmalıdır **const**. İşlenen aynı türde bir l-değeri sonucudur.  
  
 Önek azaltma işleci (**--**) önek artırma işleci için işlenen tarafından azaltılır ve sonucu indirildiği bu değerdir dışında benzerdir.  

 **Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): bir artış veya Azalış işlecinin işleneni türü olmayabilir `bool`.
  
 Önek ve sonek arttırma ve azaltma işleçleri kendi işlenenler etkiler. Aralarındaki en önemli fark, artış veya Azalış bir ifade değerlendirme işlemi gerçekleştirilir sırasıdır. (Daha fazla bilgi için bkz: [sonek arttırma ve azaltma işleçleri](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md).) İfade değeri işleneni değerinden farklı böylece değer ifadesi hesaplanmasında kullanılmadan önce önek formunda, artış veya Azalış gerçekleşir. İfadenin değerini işlenen değer ile aynı olacak şekilde değeri ifade hesaplanmasında kullanılan sonra sonek formunda, artış veya Azalış gerçekleşir. Örneğin, aşağıdaki baskı siparişi program "`++i = 6`":  
  
```  
// expre_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int i = 5;  
   cout << "++i = " << ++i << endl;  
}  
```  
  
 Tam sayı veya kayan tür işleneni tamsayı değeri 1 artırılır veya indirildiği. Sonuç türü işlenen türü ile aynıdır. İşaretçi türünün işleneni bu adresleri nesnesi tarafından artırılır veya indirildiği boyutudur. Bir artımlı işaretçinin sonraki nesneye işaret; Azaltılan işaretçi önceki nesneye işaret etmiyor.  
  
 Çünkü artırma ve azaltma işleçleri artırma veya azaltma işleçleri ile ifadeler kullanarak yan etkileri olan bir [önişlemci makrosu](../preprocessor/macros-c-cpp.md) istenmeyen sonuçları olabilir. Bu örneği göz önünde bulundurun:  
  
```  
// expre_Increment_and_Decrement_Operators2.cpp  
#define max(a,b) ((a)<(b))?(b):(a)  
  
int main()  
{  
   int i = 0, j = 0, k;  
   k = max( ++i, j );  
}  
```  
  
 Makro için genişletir:  
  
```  
k = ((++i)<(j))?(j):(++i);  
```  
  
 Varsa `i` büyük veya eşit `j` veya küçüktür `j` 1 ile iki kez arttırılır.  
  
> [!NOTE]
>  C++ satır içi işlevler olanlar burada açıklandığı gibi yan etkileri ortadan kaldırdığı makrolara çoğu durumda tercih edilir ve daha kapsamlı türü denetimi yapmak dil sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Önek Arttırma ve Azaltma İşleçleri](../c-language/prefix-increment-and-decrement-operators.md)