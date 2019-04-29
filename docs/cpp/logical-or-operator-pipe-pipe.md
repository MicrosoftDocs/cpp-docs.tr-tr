---
title: 'Mantıksal OR işleci: ||'
ms.date: 06/14/2018
f1_keywords:
- '||'
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
ms.openlocfilehash: 5db1af870644d1552aeac813edce0985a31d95b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368688"
---
# <a name="logical-or-operator-"></a>Mantıksal OR işleci: ||

## <a name="syntax"></a>Sözdizimi

> *mantıksal-veya-expression* **||** *mantıksal-ve-ifadesi*

## <a name="remarks"></a>Açıklamalar

Mantıksal OR işlecinin (**||**) boolean TRUE değerini döndürür veya her iki işlenen de TRUE ise ve aksi takdirde FALSE döndürür. İşlenen örtülü olarak türüne dönüştürülür **bool** önceki değerlendirme ve sonuç türüdür **bool**. Mantıksal OR'un ilişkilendirilebilirliği soldan sağadır.

Mantıksal OR işlecinin işlenenlerinin aynı türden olmasına gerek yoktur, ancak integral veya işaretçi türünde olmaları gerekir. İşlenenler, genel olarak ilişkisel veya eşitlik ifadeleridir.

İlk işlenen, mantıksal OR ifadesinin değerlendirilmesine devam edilmeden önce tamamen değerlendirilir ve tüm yan etkiler tamamlanır.

İkinci işlenen, yalnızca ilk işlenen yanlış (0) olarak değerlendirilirse değerlendirilir. Bu, mantıksal OR ifadesi doğru olduğunda ikinci işlenenin değerlendirilmesine gerek bırakmaz.

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

Yukarıdaki örnekte, `x``w`, `y` veya `z`'ye eşitse, `printf` işlevinin ikinci bağımsız değişkeni doğru olarak değerlendirilir ve 1 değeri yazdırılır. Aksi takdirde yanlış değerini ve 0 değeri yazdırılır. Bir koşulun true olarak değerlendirilen hemen sonra değerlendirme olmaktan çıkar.

## <a name="operator-keyword-for-124124"></a>İçin işleç anahtar sözcüğü&#124;&#124;

**Veya** işlecidir öğesinin metin eşdeğeridir **||**. Erişmenin iki yöntemi vardır **veya** programlarınızda işleci: üstbilgi dosyasını dahil \<iso646.h >, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırakma) derleyici seçeneği.

## <a name="example"></a>Örnek

```cpp
// expre_Logical_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate logical OR
#include <iostream>
using namespace std;
int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b || b > c yields "
         << (a < b || b > c) << endl
         << "The false expression "
         << "a > b || b > c yields "
         << (a > b || b > c) << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ yerleşik işleçler öncelik ve İlişkisellik](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Mantıksal İşleçleri](../c-language/c-logical-operators.md)