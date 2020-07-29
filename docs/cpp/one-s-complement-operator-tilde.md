---
title: 'Bire tamamlama işleci: ~'
description: C++ standart dilinin bir tamamlayıcı işleç sözdizimi ve kullanımı.
ms.date: 07/23/2020
f1_keywords:
- "~"
- compl_cpp
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
ms.openlocfilehash: 89c67855cd67df2af315cea941b487e7462889b2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227250"
---
# <a name="ones-complement-operator-"></a>Bire tamamlama işleci: ~

## <a name="syntax"></a>Sözdizimi

```cpp
~ cast-expression
```

## <a name="remarks"></a>Açıklamalar

Bir tamamlama işleci ( **`~`** ), bazen *bit düzeyinde tamamlayıcı* işleci olarak da adlandırılır, bir bit düzeyinde bir birinin işleneninin tamamlayıcı değerini verir. Yani, işlenende 1 olan her bit sonuçta 0'dır. Buna karşılık, işlenende 0 olan her bit sonuçta 1'dir. Birinin tamamlayıcı işlecinin işleneni integral türünde olmalıdır.

## <a name="operator-keyword-for-"></a>~ İçin işleç anahtar sözcüğü

C++, **`compl`** için alternatif bir yazım biçimi belirler **`~`** . C 'de alternatif yazım, üst bilgide bir makro olarak sağlanır \<iso646.h> . C++ ' da, alternatif yazım bir anahtar sözcüktür; \<iso646.h>C++ eşdeğeri veya kullanımı \<ciso646> kullanım dışıdır. Microsoft C++ ' da, [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) alternatif yazımı etkinleştirmek için veya derleyici seçeneği gereklidir.

## <a name="example"></a>Örnek

```cpp
// expre_One_Complement_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main () {
   unsigned short y = 0xFFFF;
   cout << hex << y << endl;
   y = ~y;   // Take one's complement
   cout << hex << y << endl;
}
```

Bu örnekte, `y`'ye atanan yeni değer işaretsiz 0xFFFF değerinin veya 0x0000 için birinin tamamlayıcısıdır.

İntegral işlenenlerde integral yükseltme gerçekleştirilir. İşlenenin yükseltilen tür, sonuç türüdür. İntegral yükseltme hakkında daha fazla bilgi için bkz. [Standart dönüştürmeler](standard-conversions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Birli işleçli ifadeler](expressions-with-unary-operators.md)<br/>
[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Birli aritmetik işleçler](../c-language/unary-arithmetic-operators.md)
