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
ms.openlocfilehash: 94b2bc024dd7223ac7adacc72924f5ee289bab37
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178086"
---
# <a name="logical-or-operator-"></a>Mantıksal OR işleci: ||

## <a name="syntax"></a>Sözdizimi

> mantıksal *or* -ifadesi **||** *mantıksal and ifadesi*

## <a name="remarks"></a>Açıklamalar

Mantıksal OR işleci ( **||** ), her iki IŞLENEN de TRUE ise true Boole değerini döndürür ve aksı takdirde false döndürür. İşlenenler, değerlendirmeden önce örtük olarak **bool** türüne dönüştürülür ve sonuç **bool**türündedir. Mantıksal OR'un ilişkilendirilebilirliği soldan sağadır.

Mantıksal OR işlecinin işlenenlerinin aynı türden olmasına gerek yoktur, ancak integral veya işaretçi türünde olmaları gerekir. İşlenenler, genel olarak ilişkisel veya eşitlik ifadeleridir.

İlk işlenen, mantıksal OR ifadesinin değerlendirilmesine devam edilmeden önce tamamen değerlendirilir ve tüm yan etkiler tamamlanır.

İkinci işlenen, yalnızca ilk işlenen yanlış (0) olarak değerlendirilirse değerlendirilir. Bu, mantıksal OR ifadesi doğru olduğunda ikinci işlenenin değerlendirilmesine gerek bırakmaz.

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

Yukarıdaki örnekte, `x``w`, `y` veya `z`'ye eşitse, `printf` işlevinin ikinci bağımsız değişkeni doğru olarak değerlendirilir ve 1 değeri yazdırılır. Aksi takdirde, false olarak değerlendirilir ve 0 değeri yazdırılır. Koşullardan biri doğru olarak değerlendirildiğinde değerlendirme sona erer.

## <a name="operator-keyword-for-124124"></a>İçin işleç anahtar sözcüğü&#124;&#124;

**Or** işleci **||** metin eşdeğeridir. Programlarınızda **or** işlecine erişmenin iki yolu vardır: \<iso646. h > üstbilgi dosyasını dahil edin veya [/za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneğiyle derleyin.

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

[C++Yerleşik operatörler öncelik ve birleşim](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Mantıksal İşleçleri](../c-language/c-logical-operators.md)
