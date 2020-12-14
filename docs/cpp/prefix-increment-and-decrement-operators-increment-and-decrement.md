---
description: 'Daha fazla bilgi edinin: önek artırma ve azaltma Işleçleri: + + ve--'
title: 'Önek Arttırma ve Azaltma İşleçleri: ++ ve --'
ms.date: 11/04/2016
f1_keywords:
- --
- ++
helpviewer_keywords:
- increment operators [C++], syntax
- ++ operator [C++], prefix increment operators
- operators [C++], decrement
- -- operator [C++], prefix decrement operators [C++]
- operators [C++], increment
- decrement operators [C++], syntax
- decrement operators [C++]
ms.assetid: 45ea7fc7-f279-4be9-a216-1d9a0ef9eb7b
ms.openlocfilehash: e484dde59a2bb58e7c408ad28242fc0ab4290051
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198648"
---
# <a name="prefix-increment-and-decrement-operators--and---"></a>Önek Arttırma ve Azaltma İşleçleri: ++ ve --

## <a name="syntax"></a>Syntax

```
++ unary-expression
-- unary-expression
```

## <a name="remarks"></a>Açıklamalar

Ön ek artırma işleci ( **++** ) işleneni bir tane ekler; Bu arttırılan değer ifadenin sonucudur. İşlenen, tür olmayan bir l değeri olmalıdır **`const`** . Sonuç, işleneniyle aynı türdeki bir l değeridir.

Önek azaltma işleci ( **--** ) önek artışı işlecine benzerdir, bu da işlenenin bir tane tarafından azaltılmasının yanı sıra bu değerin azalmasını sağlar.

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): artırma veya azaltma işlecinin işleneni türünde olamaz **`bool`** .

Ön ek ve sonek artırma ve azaltma işleçleri işlenenlerini etkiler. Aralarındaki temel fark, bir ifadenin değerlendirmesinde artış veya azalış gerçekleştiği sıradır. (Daha fazla bilgi için bkz. [sonek artırma ve azaltma işleçleri](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md).) Önek formunda, değer ifade değerlendirmesinde kullanılmadan önce artış veya azaltma gerçekleştirilir, bu nedenle ifadenin değeri işlenenin değerinden farklı olur. Sonek formunda, değer ifade değerlendirmesinde kullanıldıktan sonra artırma veya azaltma gerçekleştirilir, bu nedenle ifadenin değeri işlenenin değeri ile aynıdır. Örneğin, aşağıdaki program " `++i = 6` " yazdırır:

```cpp
// expre_Increment_and_Decrement_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   int i = 5;
   cout << "++i = " << ++i << endl;
}
```

İntegral veya kayan türün işleneni, 1 tamsayı değeri tarafından artırılır veya azaltılır. Sonucun türü, işlenen türüyle aynıdır. İşaretçi türündeki bir işlenen, adreslenen nesnenin boyutuyla artırılır veya azaltılır. Artan bir işaretçi sonraki nesneye işaret eder; azaltma işaretçisi önceki nesneye işaret eder.

Artırma ve azaltma işleçleri yan etkilere sahip olduğundan, bir [Önişlemci makrosunda](../preprocessor/macros-c-cpp.md) artırma veya azaltma işleçleri olan ifadelerin kullanılması istenmeyen sonuçlara neden olabilir. Bu örneği ele alalım:

```cpp
// expre_Increment_and_Decrement_Operators2.cpp
#define max(a,b) ((a)<(b))?(b):(a)

int main()
{
   int i = 0, j = 0, k;
   k = max( ++i, j );
}
```

Makro şu şekilde genişletilir:

```cpp
k = ((++i)<(j))?(j):(++i);
```

`i`1 ' den büyük veya bu değere eşit `j` veya bundan küçükse `j` , iki kez artırılır.

> [!NOTE]
> C++ satır içi işlevleri, burada açıklananlar gibi yan etkileri ortadan kaldırdıklarından ve dilin daha kapsamlı bir tür denetimi gerçekleştirmesine izin veren birçok durumda makrolara tercih edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Ön ek artırma ve azaltma Işleçleri](../c-language/prefix-increment-and-decrement-operators.md)
