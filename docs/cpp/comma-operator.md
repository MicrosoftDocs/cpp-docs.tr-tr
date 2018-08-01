---
title: Virgül işleci:, | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '%2C'
dev_langs:
- C++
helpviewer_keywords:
- comma operator
ms.assetid: 38e0238e-19da-42ba-ae62-277bfdab6090
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a139efed1fadd8f7b821363b7cb9cdbf97c9a29
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408646"
---
# <a name="comma-operator-"></a>Virgül İşleci: ,
Bir deyim beklenirken iki deyimin gruplandırılmasını sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
expression , expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Virgül işleci soldan sağa ilişkilendirilebilirlik vardır. Virgülle ayrılmış iki ifade, soldan sağa doğru değerlendirilir. Sol işlenen her zaman değerlendirilir ve tüm yan etkileri sağ işlenen değerlendirilmeden önce tamamlanır.  
  
 Virgüller, işlev bağımsız değişken listeleri gibi bazı bağlamlarda ayırıcılar olarak kullanılabilir. Ayırıcı olarak virgül kullanımını işleç olarak kullanımıyla karıştırmayın; iki kullanım birbirinden tamamen farklıdır.  
  
 Şu ifadeyi göz önünde bulundurun  
  
 *E1* , *e2*  
  
 Tür ve ifade değeri türü ve değeri olan *e2*; değerlendirme sonucu *e1* atılır. Sağ işlenen l değeriyse, sonuç bir l değeri olur.  
  
 Virgülün normalde bir ayırıcı olarak kullanıldığı yerlerde (örneğin, işlevlerin veya toplama başlatıcılarının gerçek bağımsız değişkenlerinde), virgül işleci ve işlenenleri parantez içine alınmalıdır. Örneğin:  
  
```cpp 
func_one( x, y + 2, z );  
func_two( (x--, y + 2), z );  
```  
  
 Yukarıdaki `func_one` işlev çağrısında, virgülle ayrılmış üç bağımsız değişken geçirilir: `x`, `y + 2` ve `z`. `func_two` işlev çağrısında, parantezler derleyiciyi, ilk virgülü sıralı değerlendirme işleci olarak yorumlamaya zorlar. Bu işlev çağrısı, `func_two` öğesine iki bağımsız değişken geçirir. İlk bağımsız değişken, `(x--, y + 2)` ifadesinin değerine ve türüne sahip olan `y + 2` sıralı değerlendirme işleminin sonucudur; ikinci bağımsız değişken ise `z`'dir.  
  
## <a name="example"></a>Örnek  
  
```cpp 
// cpp_comma_operator.cpp  
#include <stdio.h>  
int main () {  
   int i = 10, b = 20, c= 30;  
   i = b, c;  
   printf("%i\n", i);  
  
   i = (b, c);  
   printf("%i\n", i);  
}  
```  
  
```Output  
20  
30  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Sıralı Değerlendirme İşleci](../c-language/sequential-evaluation-operator.md)