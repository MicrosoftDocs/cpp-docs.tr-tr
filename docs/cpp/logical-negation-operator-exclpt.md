---
title: 'Mantıksal Değilleme İşleci: ! | Microsoft Docs'
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs:
- C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4594a8b1a881b6fa92909e7c7014087ff6240de8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211824"
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
