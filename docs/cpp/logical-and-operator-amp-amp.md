---
title: 'Mantıksal AND işleci: &amp;&amp;'
ms.date: 11/04/2016
f1_keywords:
- '&&'
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
ms.openlocfilehash: 0843ba95467c3ae0d735476de48a8195a59788f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368662"
---
# <a name="logical-and-operator-ampamp"></a>Mantıksal AND işleci: &amp;&amp;

## <a name="syntax"></a>Sözdizimi

```
expression && expression
```

## <a name="remarks"></a>Açıklamalar

Mantıksal AND işleci (**&&**) her iki işlenen de TRUE ise, boolean TRUE değerini döndürür ve aksi takdirde FALSE döndürür. İşlenen örtülü olarak türüne dönüştürülür **bool** önceki değerlendirme ve sonuç türüdür **bool**. Mantıksal AND soldan sağa ilişkilendirilebilirlik vardır.

Mantıksal AND işlecinin işlenenleri aynı türde olması gerekmez, ancak bunlar olmalıdır integral veya işaretçi türü. İşlenenler, genel olarak ilişkisel veya eşitlik ifadeleridir.

İlk işleneni tamamen değerlendirilir ve mantıksal AND ifadesi değerlendirmesi devam etmeden önce tüm yan etkiler tamamlanır.

Yalnızca ilk işlenen true (sıfırdan farklı) olarak değerlendirilirse, ikinci işlenenin değerlendirilir. Bu değerlendirme mantıksal AND ifadesi false olduğunda ikinci işlenenin değerlendirilmesine ortadan kaldırır. Bu null işaretçisinin başvurusunun kaldırılması, önlemek için aşağıdaki örnekte gösterildiği gibi kısa devre değerlendirmesi:

```cpp
char *pch = 0;
...
(pch) && (*pch = 'a');
```

Varsa `pch` null ifadesinin sağ tarafı (0), hiçbir zaman değerlendirilir. Bu nedenle, bir null işaretçi aracılığıyla atanabilecek mümkün değildir.

## <a name="operator-keyword-for-"></a>İçin işleç anahtar sözcüğü & &

**Ve** işlecidir öğesinin metin eşdeğeridir **&&**. Erişmenin iki yöntemi vardır **ve** programlarınızda işleci: üstbilgi dosyasını dahil `iso646.h`, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırakma) derleyici seçeneği.

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

[C++ yerleşik işleçler öncelik ve İlişkisellik](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Mantıksal İşleçleri](../c-language/c-logical-operators.md)