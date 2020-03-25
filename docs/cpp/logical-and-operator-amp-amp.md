---
title: 'Mantıksal AND Işleci: &amp;&amp;'
ms.date: 11/04/2016
f1_keywords:
- '&&'
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
ms.openlocfilehash: b21d91009c455b67af6fae88fceafeeaf8043301
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179438"
---
# <a name="logical-and-operator-ampamp"></a>Mantıksal AND Işleci: &amp;&amp;

## <a name="syntax"></a>Sözdizimi

```
expression && expression
```

## <a name="remarks"></a>Açıklamalar

Mantıksal AND işleci ( **&&** ), her iki IŞLENEN de TRUE ise true değerini döndürür ve aksı takdirde false döndürür. İşlenenler, değerlendirmeden önce örtük olarak **bool** türüne dönüştürülür ve sonuç **bool**türündedir. Mantıksal ve, soldan sağa ilişkilendiriledir.

Mantıksal AND işlecinin işlenenleri aynı türde olmamalıdır, ancak integral veya işaretçi türünde olmalıdır. İşlenenler, genel olarak ilişkisel veya eşitlik ifadeleridir.

İlk işlenen tamamen değerlendirilir ve mantıksal ve ifade değerlendirmesi devam etmeden önce tüm yan etkiler tamamlanır.

İkinci işlenen, yalnızca ilk işlenen true (sıfır dışında) olarak değerlendirilirse değerlendirilir. Bu değerlendirme, mantıksal AND ifadesi false olduğunda ikinci işlenenin gereksiz değerlendirmesini ortadan kaldırır. Aşağıdaki örnekte gösterildiği gibi, null işaretçi başvurusunu engellemek için bu kısa devre değerlendirmesini kullanabilirsiniz:

```cpp
char *pch = 0;
...
(pch) && (*pch = 'a');
```

`pch` null (0) ise, ifadenin sağ tarafı hiçbir şekilde değerlendirilmez. Bu nedenle, null bir işaretçi aracılığıyla atama olanaksızdır.

## <a name="operator-keyword-for-"></a>& & İçin işleç anahtar sözcüğü

**And** işleci **&&** metin eşdeğeridir. Programlarınızda **ve** işlecine erişmenin iki yolu vardır: `iso646.h`üst bilgi dosyasını dahil edin veya [/za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneğiyle derleyin.

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

[C++Yerleşik operatörler öncelik ve birleşim](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Mantıksal İşleçleri](../c-language/c-logical-operators.md)
