---
title: 'Mantıksal Değilleme İşleci: !'
ms.date: 08/27/2018
f1_keywords:
- '!'
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: 06142ef15fcdbafdbae4b892772a04b117c087f6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446546"
---
# <a name="logical-negation-operator-"></a>Mantıksal Değilleme İşleci: !

## <a name="syntax"></a>Sözdizimi

```
! cast-expression
```

## <a name="remarks"></a>Açıklamalar

Mantıksal Değilleme İşleci ( **!** ), işleneninin anlamını tersine çevirir. İşlenen, aritmetik veya işaretçi türünde (veya aritmetik ya da işaretçi türü olarak değerlendirilen bir ifade) olmalıdır. İşlenen örtük olarak **bool**türüne dönüştürülür. Dönüştürülen işlenen FALSE ise sonuç doğrudur; dönüştürülmüş işlenen TRUE ise sonuç FALSE 'TUR. Sonuç **bool**türündedir.

*E*ifadesi için, `!e` birli ifade, aşırı yüklenmiş işleçlerin dahil olduğu durumlar dışında `(e == 0)`ifade ile eşdeğerdir.

## <a name="operator-keyword-for-"></a>! için İşleç Anahtar Sözcüğü

**Not** işleci, **!** için alternatif bir yazıdır. Programlarınızda **Not** operatörüne erişmenin iki yolu vardır: \<iso646. h > üst bilgi dosyasını dahil edin veya [/za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneğiyle derleyin.

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
