---
title: 'Eşitlik işleçleri: == ve! = | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- not_eq
- '!='
- ==
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1072892c4ad69396c62a728f7e828e9c683d155
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068487"
---
# <a name="equality-operators--and-"></a>Eşitlik İşleçleri: == ve !=

## <a name="syntax"></a>Sözdizimi

```
expression == expression
expression != expression
```

## <a name="remarks"></a>Açıklamalar

İkili eşitlik işleçleri işlenenleri katı eşitlik ve eşitsizlik için karşılaştırın.

Eşitlik işleçleri eşit (`==`) ve eşit değildir (`!=`), ilişkisel işleçler daha düşük önceliğe sahip, ancak benzer şekilde davranır. Bu işleçler için sonuç türü **bool**.

Eşittir işleci (`==`) döndürür **true** (1) Eğer her iki işlenen de aynı değere sahip; Aksi halde **false** (0). Not-eşittir operatörü (`!=`) döndürür **true** işlenenler aynı değeri; yoksa, aksi halde döndürür **false**.

## <a name="operator-keyword-for-"></a>İçin işleç anahtar sözcüğü! =

`not_eq` işleci, `!=` öğesinin metin eşdeğeridir. Erişmenin iki yöntemi vardır `not_eq` programlarınızda işleci: üstbilgi dosyasını dahil `iso646.h`, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırakma) derleyici seçeneği.

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

Eşitlik işleçleri, aynı türde üye işaretçileri karşılaştırabilirsiniz. Böyle bir Karşılaştırmada işaretçi-üye dönüşümleri gerçekleştirilir. Üye işaretçileri için 0 olarak değerlendirilen sabit bir ifade ayrıca karşılaştırılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[İkili İşleçli İfadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C İlişkisel ve Eşitlik İşleçleri](../c-language/c-relational-and-equality-operators.md)