---
title: 'Mantıksal değilleme işleci: !'
description: C++ standart dil mantıksal değilleme işleci sözdizimi ve kullanımı.
ms.date: 07/23/2020
f1_keywords:
- '!'
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: fdd2e7a71b791375f898372d058a5eeb2afc59f1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223687"
---
# <a name="logical-negation-operator-"></a>Mantıksal değilleme işleci: !

## <a name="syntax"></a>Sözdizimi

> **`!`***Cast ifadesi*

## <a name="remarks"></a>Açıklamalar

Mantıksal olumsuzlama işleci ( **`!`** ), işleneninin anlamını tersine çevirir. İşlenen, aritmetik veya işaretçi türünde (veya aritmetik ya da işaretçi türü olarak değerlendirilen bir ifade) olmalıdır. İşlenen örtük olarak türüne dönüştürülür **`bool`** . Sonuç, dönüştürülmüş işlenen ise sonuç, **`true`** **`false`** **`false`** dönüştürülmüş işlenenin ise olur **`true`** . Sonuç türü **`bool`** .

Bir ifade için `e` , bir birli ifade `!e` `(e == 0)` , aşırı yüklenmiş işleçlerin dahil olduğu durumlar dışında ifadeye eşdeğerdir.

## <a name="operator-keyword-for-"></a>İçin işleç anahtar sözcüğü

C++, **`not`** için alternatif bir yazım biçimi belirler **`!`** . C 'de alternatif yazım, üst bilgide bir makro olarak sağlanır \<iso646.h> . C++ ' da, alternatif yazım bir anahtar sözcüktür; \<iso646.h>C++ eşdeğeri veya kullanımı \<ciso646> kullanım dışıdır. Microsoft C++ ' da, [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) alternatif yazımı etkinleştirmek için veya derleyici seçeneği gereklidir.

## <a name="example"></a>Örnek

```cpp
// expre_Logical_NOT_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    if (!i)
        cout << "i is zero" << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Birli aritmetik işleçler](../c-language/unary-arithmetic-operators.md)<br/>
