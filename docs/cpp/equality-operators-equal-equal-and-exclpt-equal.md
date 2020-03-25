---
title: 'Eşitlik İşleçleri: == ve !='
ms.date: 11/04/2016
f1_keywords:
- '!='
- ==
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
ms.openlocfilehash: 8a0c08f438528caeaac6d5e52e806a36fe56dd25
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189253"
---
# <a name="equality-operators--and-"></a>Eşitlik İşleçleri: == ve !=

## <a name="syntax"></a>Sözdizimi

```
expression == expression
expression != expression
```

## <a name="remarks"></a>Açıklamalar

İkili eşitlik işleçleri işlenenlerini katı eşitlik veya eşitsizlik için karşılaştırır.

Eşitlik işleçleri (`==`) ve eşit değildir (`!=`), ilişkisel işleçlerden daha düşük önceliğe sahiptir, ancak benzer şekilde davranır. Bu işleçler için sonuç türü **bool**olur.

Eşittir işleci (`==`), her iki işlenen de aynı değere sahip olursa **true** (1) döndürür. Aksi takdirde, **false** (0) değerini döndürür. Eşit olmayan işleç (`!=`), işlenenler aynı değere sahip değilse **true** değerini döndürür; Aksi takdirde, **false**döndürür.

## <a name="operator-keyword-for-"></a>! = İçin işleç anahtar sözcüğü

`not_eq` işleci, `!=` öğesinin metin eşdeğeridir. Programlarınızda `not_eq` işlecine erişmenin iki yolu vardır: üstbilgi dosyasını `iso646.h`dahil edin veya [/za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneğiyle derleyin.

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

[İkili İşleçli İfadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C İlişkisel ve Eşitlik İşleçleri](../c-language/c-relational-and-equality-operators.md)
