---
title: "Sonek artırma ve azaltma işleçleri: ++ ve--| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- --
- ++
dev_langs: C++
helpviewer_keywords:
- increment operators [C++], syntax
- member-selection operators [C++]
- -- operator [C++], postfix decrement operators
- postfix operators [C++]
- ++ operator [C++], postfix increment operators
- decrement operators [C++], syntax
- operators [C++], postfix
- decrement operators [C++]
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cbf22e57abaefc7b14be9c4eab404f7c20cb9359
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="postfix-increment-and-decrement-operators--and---"></a>Sonek Arttırma ve Azaltma İşleçleri: ++ ve --
## <a name="syntax"></a>Sözdizimi  
  
```  
postfix-expression ++  
postfix-expression --  
```  
  
## <a name="remarks"></a>Açıklamalar  
 C++ önek ve sonek artırma ve azaltma işleçleri sağlar; bu bölümde yalnızca sonek artırma ve azaltma işleçleri açıklanmaktadır. (Daha fazla bilgi için bkz: [önek arttırma ve azaltma işleçleri](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md).) İkisi arasındaki farkı sonek gösterimde sonra işleci görünen addır *sonek ifade*, önek gösterimde önce işleci görünürken *ifade.* Aşağıdaki örnekte, bir sonek artırma işleci gösterilmektedir:  
  
```  
i++;  
```  
  
 Sonek artırma işlecini (`++`) uygulamanın etkisi, işlenenin değerinin uygun türde bir birim artırılmasıdır. Benzer şekilde, sonek azaltma işleci uygulama etkisini (**--**) işleneni 's değeri uygun türde bir birim azalır olduğu.  
  
 Bir sonek Artır olduğunu dikkate almak önemlidir veya azaltma ifadeyi hesaplar ifadenin değerini **öncesinde** ilgili işlecinin uygulama. Artırma veya azaltma işlemi gerçekleşir **sonra** işleneni değerlendirilir. Bu sorun, yalnızca sonek artırma veya azaltma işlevi daha büyük bir ifadenin bağlamında gerçekleştiğinde ortaya çıkar.  
  
 Bir sonek işleci bir işlevin bağımsız değişkenine uygulandığında, bağımsız değişkenin değerinin işleve geçirilmeden önce artırılması veya azaltılması garanti edilmez.  Daha fazla bilgi için C++ standardındaki 1.9.17 bölümüne bakın.  
  
 Sonek artırma işlecinin türündeki nesneler dizisi için bir işaretçi uygulayarak **uzun** gerçekten dört işaretçinin iç gösterimi ekler. Daha önce başvurulan işaretçi bu davranışa neden  *n* başvurmak için bu dizinin th öğesi (*n*+ 1) th öğesi.  
  
 Sonek artırma ve azaltma işleçleri sonek işlenenleri değiştirilebilir olmalıdır (değil **const**) l değerleri aritmetik veya işaretçi türü. Sonuç türü aynıdır *sonek ifade*, ancak artık l-değeri değil.  
  
**Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): işleneni bir sonek artırma veya azaltma işleci türü olmayabilir `bool`.
  
 Aşağıdaki kod sonek artırma işlecini gösterir:  
  
```  
// expre_Postfix_Increment_and_Decrement_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 10;  
   cout << i++ << endl;  
   cout << i << endl;  
}  
```  
  
 Numaralandırılmış türler üzerinde postincrement ve postdecrement işlemleri desteklenmez:  
  
```  
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonek ifadeleri](../cpp/postfix-expressions.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C sonek arttırma ve azaltma işleçleri](../c-language/c-postfix-increment-and-decrement-operators.md)