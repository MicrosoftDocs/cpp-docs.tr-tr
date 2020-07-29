---
title: 'Eşitlik işleçleri: == ve !='
description: C++ standart dili eşittir ve eşit değildir işleç sözdizimi ve kullanımı.
ms.date: 07/23/2020
f1_keywords:
- '!='
- ==
- not_eq_cpp
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
ms.openlocfilehash: 567b83e99dce0354626f08a4788f1343314493b1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227549"
---
# <a name="equality-operators--and-"></a>Eşitlik işleçleri: == ve !=

## <a name="syntax"></a>Sözdizimi

> *ifade* **`==`** *ifade*\
> *ifade* **`!=`** *ifade*

## <a name="remarks"></a>Açıklamalar

İkili eşitlik işleçleri işlenenlerini katı eşitlik veya eşitsizlik için karşılaştırır.

Eşitlik işleçleri ( **`==`** ) ve eşit değildir ( **`!=`** ), ilişkisel işleçlerden daha düşük önceliğe sahiptir, ancak benzer şekilde davranır. Bu işleçler için sonuç türü **`bool`** .

Eşittir işleci ( **`==`** ), **`true`** her iki işlenen de aynı değere sahip olursa döndürür; Aksi takdirde, döndürür **`false`** . Eşit olmayan işleç ( **`!=`** ), **`true`** işlenenler aynı değere sahip değilse döndürür; Aksi takdirde, döndürür **`false`** .

## <a name="operator-keyword-for-"></a>! = İçin işleç anahtar sözcüğü

C++, **`not_eq`** için alternatif bir yazım biçimi belirler **`!=`** . (İçin alternatif yazım yok **`==`** .) C 'de alternatif yazım, üst bilgide bir makro olarak sağlanır \<iso646.h> . C++ ' da, alternatif yazım bir anahtar sözcüktür; \<iso646.h>C++ eşdeğeri veya kullanımı \<ciso646> kullanım dışıdır. Microsoft C++ ' da, [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) alternatif yazımı etkinleştirmek için veya derleyici seçeneği gereklidir.

## <a name="example"></a>Örnek

```cpp
// expre_Equality_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   cout  << boolalpha
         << "The true expression 3 != 2 yields: "
         << (3 != 2) << endl
         << "The false expression 20 == 10 yields: "
         << (20 == 10) << endl;
}
```

Eşitlik işleçleri aynı türdeki üyelerle işaretçileri karşılaştırabilirler. Böyle bir karşılaştırma için, üye işaretçisi dönüştürmeleri gerçekleştirilir. Üye işaretçileri, 0 olarak değerlendirilen bir sabit ifadeyle da karşılaştırılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ yerleşik işleçleri, önceliği; ve ilişkilendirilebilirlik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C ilişkisel ve eşitlik işleçleri](../c-language/c-relational-and-equality-operators.md)
