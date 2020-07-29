---
title: Mantıksal AND Işleci:&amp;&amp;
description: C++ standart dil mantıksal ve işleç sözdizimi ve kullanımı.
ms.date: 07/23/2020
f1_keywords:
- '&&'
- and_cpp
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
ms.openlocfilehash: 431e76a2943c2373d6191f1fbe9f14c54cfaa6c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223700"
---
# <a name="logical-and-operator-ampamp"></a>Mantıksal AND işleci:&amp;&amp;

## <a name="syntax"></a>Sözdizimi

> *ifade* **`&&`** *ifade*

## <a name="remarks"></a>Açıklamalar

Mantıksal AND işleci ( **&&** ), **`true`** her iki işlenen de varsa döndürür **`true`** ve **`false`** Aksi takdirde döndürür. İşlenenler, değerlendirmeden önce örtük olarak türüne dönüştürülür **`bool`** ve sonuç tür olur **`bool`** . Mantıksal ve, soldan sağa ilişkilendiriledir.

Mantıksal AND işlecinin işlenenleri aynı türde olması gerekmez, ancak Boolean, integral veya işaretçi türüne sahip olmalıdır. İşlenenler, genel olarak ilişkisel veya eşitlik ifadeleridir.

İlk işlenen tamamen değerlendirilir ve mantıksal ve ifade değerlendirmesi devam etmeden önce tüm yan etkiler tamamlanır.

İkinci işlenen, yalnızca ilk işlenen **`true`** (sıfır dışında) olarak değerlendirilirse değerlendirilir. Bu değerlendirme, mantıksal ve ifade olduğunda ikinci işlenenin gereksiz değerlendirmesini ortadan kaldırır **`false`** . Aşağıdaki örnekte gösterildiği gibi, null işaretçi başvurusunu engellemek için bu kısa devre değerlendirmesini kullanabilirsiniz:

```cpp
char *pch = 0;
// ...
(pch) && (*pch = 'a');
```

`pch`Null (0) ise, ifadenin sağ tarafı hiçbir şekilde değerlendirilmez. Bu kısa devre değerlendirmesi, atamayı boş bir işaretçi ile mümkün olmayan şekilde yapar.

## <a name="operator-keyword-for-"></a> && için işleç anahtar sözcüğü

C++, **`and`** için alternatif bir yazım biçimi belirler **`&&`** . C 'de alternatif yazım, üst bilgide bir makro olarak sağlanır \<iso646.h> . C++ ' da, alternatif yazım bir anahtar sözcüktür; \<iso646.h>C++ eşdeğeri veya kullanımı \<ciso646> kullanım dışıdır. Microsoft C++ ' da, [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) alternatif yazımı etkinleştirmek için veya derleyici seçeneği gereklidir.

## <a name="example"></a>Örnek

```cpp
// expre_Logical_AND_Operator.cpp
// compile with: /EHsc
// Demonstrate logical AND
#include <iostream>

using namespace std;

int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b && b < c yields "
         << (a < b && b < c) << endl
         << "The false expression "
         << "a > b && b < c yields "
         << (a > b && b < c) << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C mantıksal işleçleri](../c-language/c-logical-operators.md)
