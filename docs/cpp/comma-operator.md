---
title: 'Virgül İşleci: ,'
ms.date: 11/04/2016
f1_keywords:
- '%2C'
helpviewer_keywords:
- comma operator
ms.assetid: 38e0238e-19da-42ba-ae62-277bfdab6090
ms.openlocfilehash: 6ea2bd5c0e7653ba7f81531a5c39df2da41662a9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189773"
---
# <a name="comma-operator-"></a>Virgül İşleci: ,

Bir deyim beklenirken iki deyimin gruplandırılmasını sağlar.

## <a name="syntax"></a>Sözdizimi

```
expression , expression
```

## <a name="remarks"></a>Açıklamalar

Virgül işleci soldan sağa ilişkilendiriledir. Virgülle ayrılmış iki ifade, soldan sağa doğru değerlendirilir. Sol işlenen her zaman değerlendirilir ve tüm yan etkileri sağ işlenen değerlendirilmeden önce tamamlanır.

Virgüller, işlev bağımsız değişken listeleri gibi bazı bağlamlarda ayırıcılar olarak kullanılabilir. Ayırıcı olarak virgül kullanımını işleç olarak kullanımıyla karıştırmayın; iki kullanım birbirinden tamamen farklıdır.

`e1, e2` ifadesini göz önünde bulundurun. İfadenin türü ve değeri, *E2*türü ve değeridir; *E1* 'ın değerlendirilme sonucu atılır. Sağ işlenen l değeriyse, sonuç bir l değeri olur.

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

[İkili İşleçli İfadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Sıralı Değerlendirme İşleci](../c-language/sequential-evaluation-operator.md)
