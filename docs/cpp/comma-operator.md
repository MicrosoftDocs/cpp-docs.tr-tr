---
description: 'Daha fazla bilgi: virgül Işleci:,'
title: 'Virgül İşleci: ,'
ms.date: 11/04/2016
f1_keywords:
- '%2C'
helpviewer_keywords:
- comma operator
ms.assetid: 38e0238e-19da-42ba-ae62-277bfdab6090
ms.openlocfilehash: 1429e2ce444e0f253bffca795f36f4e6194e0395
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274781"
---
# <a name="comma-operator-"></a>Virgül İşleci: ,

Bir deyim beklenirken iki deyimin gruplandırılmasını sağlar.

## <a name="syntax"></a>Syntax

```
expression , expression
```

## <a name="remarks"></a>Açıklamalar

Virgül işleci soldan sağa ilişkilendiriledir. Virgülle ayrılmış iki ifade, soldan sağa doğru değerlendirilir. Sol işlenen her zaman değerlendirilir ve tüm yan etkileri sağ işlenen değerlendirilmeden önce tamamlanır.

Virgüller, işlev bağımsız değişken listeleri gibi bazı bağlamlarda ayırıcılar olarak kullanılabilir. Ayırıcı olarak virgül kullanımını işleç olarak kullanımıyla karıştırmayın; iki kullanım birbirinden tamamen farklıdır.

`e1, e2` ifadesini göz önünde bulundurun. İfadenin türü ve değeri, *E2* türü ve değeridir; *E1* 'ın değerlendirilme sonucu atılır. Sağ işlenen l değeriyse, sonuç bir l değeri olur.

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

[Ikili Işleçlere sahip ifadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Sıralı değerlendirme Işleci](../c-language/sequential-evaluation-operator.md)
