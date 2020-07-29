---
title: 'Mantıksal OR işleci:  &#124;&#124;'
description: C++ standart dil mantıksal veya işleç sözdizimi ve kullanımı.
ms.date: 07/23/2020
f1_keywords:
- '||'
- or_cpp
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
ms.openlocfilehash: 1845aef59f88d5dd044cefedd21cb618e1102e13
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226001"
---
# <a name="logical-or-operator-124124"></a>Mantıksal OR işleci:  &#124;&#124;

## <a name="syntax"></a>Sözdizimi

> *mantıksal or ifadesi* **`||`** *mantıksal and ifadesi*

## <a name="remarks"></a>Açıklamalar

Mantıksal OR işleci (), ya **`||`** **`true`** da her iki işlenen ise Boolean değeri döndürür **`true`** ve **`false`** Aksi takdirde döndürür. İşlenenler, değerlendirmeden önce örtük olarak türüne dönüştürülür **`bool`** ve sonuç tür olur **`bool`** . Mantıksal OR'un ilişkilendirilebilirliği soldan sağadır.

Mantıksal OR işlecinin işlenenleri aynı türde değil, ancak Boolean, integral veya işaretçi türünde olmalıdır. İşlenenler, genel olarak ilişkisel veya eşitlik ifadeleridir.

İlk işlenen, mantıksal OR ifadesinin değerlendirilmesine devam edilmeden önce tamamen değerlendirilir ve tüm yan etkiler tamamlanır.

İkinci işlenen, **`false`** MANTıKSAL or ifadesi olduğunda değerlendirme gerekli olmadığından, yalnızca ilk işlenen olarak değerlendirilirse değerlendirilir **`true`** . Bu, *kısa devre* değerlendirmesi olarak bilinir.

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

Yukarıdaki örnekte,,, `x` veya değerine eşitse, `w` `y` `z` işlevin ikinci bağımsız değişkeni `printf` olarak değerlendirilir **`true`** ve bu da bir tamsayıya yükseltilir ve 1 değeri yazdırılır. Aksi takdirde, olarak değerlendirilir **`false`** ve 0 değeri yazdırılır. Koşullardan biri olarak değerlendirdiği anda **`true`** değerlendirme duraklar.

## <a name="operator-keyword-for-124124"></a> &#124;&#124; için işleç anahtar sözcüğü

C++, **`or`** için alternatif bir yazım biçimi belirler **`||`** . C 'de alternatif yazım, üst bilgide bir makro olarak sağlanır \<iso646.h> . C++ ' da, alternatif yazım bir anahtar sözcüktür; \<iso646.h>C++ eşdeğeri veya kullanımı \<ciso646> kullanım dışıdır. Microsoft C++ ' da, [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) alternatif yazımı etkinleştirmek için veya derleyici seçeneği gereklidir.

## <a name="example"></a>Örnek

```cpp
// expre_Logical_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate logical OR
#include <iostream>
using namespace std;
int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b || b > c yields "
         << (a < b || b > c) << endl
         << "The false expression "
         << "a > b || b > c yields "
         << (a > b || b > c) << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C mantıksal işleçleri](../c-language/c-logical-operators.md)
