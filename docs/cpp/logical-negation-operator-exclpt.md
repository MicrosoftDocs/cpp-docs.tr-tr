---
title: 'Mantıksal Değilleme İşleci: !'
ms.date: 08/27/2018
f1_keywords:
- '!'
- Not
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: 7b37e5108ca01d782c13508c0cd7a96b096cd745
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216414"
---
# <a name="logical-negation-operator-"></a>Mantıksal Değilleme İşleci: !

## <a name="syntax"></a>Sözdizimi

```
! cast-expression
```

## <a name="remarks"></a>Açıklamalar

Mantıksal değilleme işleci (**!**), işlenenin anlamını tersine çevirir. İşlenen, aritmetik veya işaretçi türünde (veya aritmetik ya da işaretçi türü olarak değerlendirilen bir ifade) olmalıdır. İşlenen örtülü olarak türüne dönüştürülür **bool**. Dönüştürülen işlenen FALSE ise, sonuç değeri True'dur; Dönüştürülen işlenen TRUE ise sonuç FALSE olur. Sonuç türünde **bool**.

Bir ifade için *e*, birli ifadesi `!e` ifadesine eşdeğerdir `(e == 0)`, aşırı yüklenmiş işleçler dahil olduğu dışında.

## <a name="operator-keyword-for-"></a>! için İşleç Anahtar Sözcüğü

**Değil** işleci, bir alternatif yazım **!**. Erişmenin iki yöntemi vardır **değil** programlarınızda işleci: üstbilgi dosyasını dahil \<iso646.h >, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırakma) derleyici seçeneği.

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

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Birli Aritmetik İşleçler](../c-language/unary-arithmetic-operators.md)<br/>
