---
title: 'Mantıksal OR işleci: || | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '||'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ce7b3085a66cf731da4373c534a95d09225d8ae
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948019"
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

- [C++ yerleşik işleçler öncelik ve İlişkisellik](cpp-built-in-operators-precedence-and-associativity.md)
- [C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
- [C Mantıksal İşleçleri](../c-language/c-logical-operators.md)