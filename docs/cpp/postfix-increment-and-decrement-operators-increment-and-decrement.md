---
title: 'Sonek artırma ve azaltma işleçleri: ++ ve--| Microsoft Docs'
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
- member-selection operators [C++]
- -- operator [C++], postfix decrement operators
- postfix operators [C++]
- ++ operator [C++], postfix increment operators
- decrement operators [C++], syntax
- operators [C++], postfix
- decrement operators [C++]
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6021de0e012797b811fa032547f2b95142176cc
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948124"
---
# <a name="postfix-increment-and-decrement-operators--and---"></a>Sonek Arttırma ve Azaltma İşleçleri: ++ ve --
## <a name="syntax"></a>Sözdizimi  
  
```  
postfix-expression ++  
postfix-expression --  
```  
  
## <a name="remarks"></a>Açıklamalar  
 C++ önek ve sonek artırma ve azaltma işleçleri sağlar; bu bölümde yalnızca sonek artırma ve azaltma işleçleri açıklanmaktadır. (Daha fazla bilgi için [önek arttırma ve azaltma işleçleri](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md).) İkisi arasındaki fark sonek gösteriminde işleç sonra görünür olan *sonek ifadesi*, önek gösteriminde işlecin önce gösterilmesidir *ifade.* Aşağıdaki örnekte, bir sonek artırma işleci gösterilmektedir:  
  
```cpp 
i++;  
```  
  
 Sonek artırma işlecini (`++`) uygulamanın etkisi, işlenenin değerinin uygun türde bir birim artırılmasıdır. Benzer şekilde, sonek azaltma işlecini etkisi (**--**) işlenenin'ın değerinin uygun türde bir birim azaltılmasıdır.  
  
 Bir sonek artırma dikkat edin önemlidir veya azaltma ifadeyi hesaplar için ifadenin değerini *öncesinde* ilgili işlecin uygulama. Artırma veya azaltma işlemi gerçekleşir *sonra* işlenen değerlendirilir. Bu sorun, yalnızca sonek artırma veya azaltma işlevi daha büyük bir ifadenin bağlamında gerçekleştiğinde ortaya çıkar.  
  
 Bir sonek işleci bir işlevin bağımsız değişkenine uygulandığında, bağımsız değişkenin değerinin işleve geçirilmeden önce artırılması veya azaltılması garanti edilmez.  Daha fazla bilgi için C++ standardındaki 1.9.17 bölümüne bakın.  
  
 Sonek artırma işlecini bir dizi türünde nesne işaretçisi uygulama **uzun** gerçekte işaretçinin iç gösterimine dört ekler. Bu davranış neden olur, daha önce işaretçi *n*öğedeki başvurmak için bu dizinin (*n*+ 1) öğedeki.  
  
 Sonek artırma ve sonek azaltma işleçleri için işlenenler değiştirilebilir (değil **const**) aritmetik veya işaretçi türünde l değerleri. Sonuç türü olan aynıdır *sonek ifadesi*, ancak artık bir l değeri değildir.  
  
**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): işlenen işleci bir sonek artırma veya azaltma türü olmayabilir **bool**.
  
 Aşağıdaki kod sonek artırma işlecini gösterir:  
  
```cpp 
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
  
```cpp 
enum Compass { North, South, East, West );  
Compass myCompass;  
for( myCompass = North; myCompass != West; myCompass++ ) // Error  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonek ifadeleri](../cpp/postfix-expressions.md)   
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C Sonek Arttırma ve Azaltma İşleçleri](../c-language/c-postfix-increment-and-decrement-operators.md)