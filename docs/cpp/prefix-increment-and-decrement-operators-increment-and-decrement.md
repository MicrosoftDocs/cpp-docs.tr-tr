---
title: 'Önek Arttırma ve Azaltma İşleçleri: ++ ve --'
ms.date: 11/04/2016
f1_keywords:
- --
- ++
helpviewer_keywords:
- increment operators [C++], syntax
- ++ operator [C++], prefix increment operators
- operators [C++], decrement
- -- operator [C++], prefix decrement operators [C++]
- operators [C++], increment
- decrement operators [C++], syntax
- decrement operators [C++]
ms.assetid: 45ea7fc7-f279-4be9-a216-1d9a0ef9eb7b
ms.openlocfilehash: ce066a3349d56b278739f586fe851b020da78885
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366216"
---
# <a name="prefix-increment-and-decrement-operators--and---"></a>Önek Arttırma ve Azaltma İşleçleri: ++ ve --

## <a name="syntax"></a>Sözdizimi

```
++ unary-expression
-- unary-expression
```

## <a name="remarks"></a>Açıklamalar

Önek artış işleci**++**( ) bir operand ekler; bu artışlı değer ifadenin sonucudur. Operand bir l-değeri türü **const**olmamalıdır. Sonuç, operand ile aynı türden bir l değeridir.

Önek decrement işleci (**--**) önek artış işlecine benzer, ancak operand biri tarafından bir değere göre belirlenir ve sonuç bu decremented değerdir.

**Visual Studio 2017 sürüm 15.3 ve sonrası** [(/std:c++17](../build/reference/std-specify-language-standard-version.md)ile birlikte): Bir artış veya decrement işlecinin operand türü **bool**olmayabilir .

Hem önek hem de postfix artış ve decrement işleçleri operands etkiler. Aralarındaki temel fark, bir ifadenin değerlendirilmesinde artış veya değer yaratma sırasıdır. (Daha fazla bilgi için bkz: [Postfix Artış ve Kararname Operatörleri.)](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) Önek formunda, değer ifade değerlendirmesinde kullanılmadan önce artış veya decrement gerçekleşir, bu nedenle ifadenin değeri operand'ın değerinden farklıdır. Postfix formunda, değer ifade değerlendirmesinde kullanıldıktan sonra artış veya dekontur gerçekleşir, bu nedenle ifadenin değeri operand'ın değeriyle aynıdır. Örneğin, aşağıdaki program "`++i = 6`"yazdırır:

```cpp
// expre_Increment_and_Decrement_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   int i = 5;
   cout << "++i = " << ++i << endl;
}
```

İntegral veya kayan tipte bir operand, 1'in ayrılmaz değerine göre artıp veya kararnameye göre belirlenir. Sonucun türü operand tipi ile aynıdır. İşaretçi türündeki bir operand, hitap ettiği nesnenin boyutuna göre artımlı veya küçük bir değere işaretlenir. Artışlı işaretçi sonraki nesneyi işaret eder; bir kararname işaretçisi önceki nesneye işaret eder.

Artış ve decrement işleçleri yan etkileri olduğundan, [bir önişlemci makroartış](../preprocessor/macros-c-cpp.md) veya decrement işleçleri ile ifadeler kullanarak istenmeyen sonuçlar olabilir. Bu örneği göz önünde bulundurun:

```cpp
// expre_Increment_and_Decrement_Operators2.cpp
#define max(a,b) ((a)<(b))?(b):(a)

int main()
{
   int i = 0, j = 0, k;
   k = max( ++i, j );
}
```

Makro şu şekilde genişler:

```cpp
k = ((++i)<(j))?(j):(++i);
```

1'den büyük `i` `j` veya eşit `j` veya daha az ise, iki kez artımlanır.

> [!NOTE]
> C++ satır altı işlevleri, burada açıklananlar gibi yan etkileri ortadan kaldırdıkları ve dilin daha eksiksiz tür denetimi yapmasına izin verdikleri için birçok durumda makrolara tercih edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Önek Arttırma ve Azaltma İşleçleri](../c-language/prefix-increment-and-decrement-operators.md)
