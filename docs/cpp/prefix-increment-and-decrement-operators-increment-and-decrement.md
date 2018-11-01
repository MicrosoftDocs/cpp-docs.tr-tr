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
ms.openlocfilehash: deb8acc6c6a68c9a97f2f0efbdc4084b4937df46
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606030"
---
# <a name="prefix-increment-and-decrement-operators--and---"></a>Önek Arttırma ve Azaltma İşleçleri: ++ ve --

## <a name="syntax"></a>Sözdizimi

```
++ unary-expression
-- unary-expression
```

## <a name="remarks"></a>Açıklamalar

Önek artırma işleci (**++**) ekler; işleneni bir ifadenin sonucu artan değerdir. İşlenen türü l değeri olmalıdır **const**. İşlenen aynı türden bir l değeri sonucudur.

Önek azaltma işleci (**--**) önek artırma işleci için işlenen bir azaltılır ve sonuç indirildiği bu değer dışında benzerdir.

**Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): bir artırma veya azaltma işlecinin işleneni türü olmayabilir **bool**.

Önek ve sonek artırma ve azaltma işleçleri işlenenleri etkiler. Aralarındaki temel fark, artırma veya azaltma ifade değerlendirme işlemi gerçekleştirilir sırasıdır. (Daha fazla bilgi için [sonek arttırma ve azaltma işleçleri](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md).) İfadenin değerine işlenenin değerinden farklı olacak şekilde değeri ifade değerlendirmesinde kullanılmadan önce ön eki biçiminde artırma veya azaltma yerini alır. İfadenin değerine işlenenin değerini aynı olacak şekilde değeri ifade değerlendirmesinde kullanıldıktan sonra sonek formda artırma veya azaltma gerçekleşir. Örneğin, aşağıdaki yazdırır program "`++i = 6`":

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

Tamsayı veya kayan türünde bir işlenen, tamsayı değeri 1 artırılması veya azaltılması. Sonuç türü, işlenenin türü ile aynıdır. İşaretçi türünde bir işlenen sıra nesnesi tarafından artırılması veya azaltılması boyutudur. Artan bir işaretçi sonraki nesneye işaret eder; indirildiği işaretçi önceki nesneye işaret eder.

Çünkü artırma ve azaltma işleçleri, artırma veya azaltma işleçleri ifadeleri kullanarak yan etkileri olan bir [önişlemci makrosu](../preprocessor/macros-c-cpp.md) istenmeyen sonuçları olabilir. Bu örneği göz önünde bulundurun:

```cpp
// expre_Increment_and_Decrement_Operators2.cpp
#define max(a,b) ((a)<(b))?(b):(a)

int main()
{
   int i = 0, j = 0, k;
   k = max( ++i, j );
}
```

Makro genişletir:

```cpp
k = ((++i)<(j))?(j):(++i);
```

Varsa `i` büyüktür veya eşittir `j` veya küçüktür `j` 1 ile iki kez artırılacaktır.

> [!NOTE]
>  C++ satır içi işlevler, bunlar burada açıklananlar gibi yan etkileri ortadan kaldırdığı için çoğu durumda makroları tercih edilir ve dil daha eksiksiz tür denetimi gerçekleştirmek izin.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Önek Arttırma ve Azaltma İşleçleri](../c-language/prefix-increment-and-decrement-operators.md)