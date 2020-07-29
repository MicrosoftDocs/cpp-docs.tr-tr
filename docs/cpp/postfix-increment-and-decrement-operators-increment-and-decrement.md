---
title: 'Sonek Arttırma ve Azaltma İşleçleri: ++ ve --'
ms.date: 11/04/2016
f1_keywords:
- --
- ++
helpviewer_keywords:
- increment operators [C++], syntax
- member-selection operators [C++]
- -- operator [C++], postfix decrement operators
- postfix operators [C++]
- ++ operator [C++], postfix increment operators
- decrement operators [C++], syntax
- operators [C++], postfix
- decrement operators [C++]
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
ms.openlocfilehash: 8c3eeb47ec81f4073452c17f40eb2fec4911989f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213287"
---
# <a name="postfix-increment-and-decrement-operators--and---"></a>Sonek Arttırma ve Azaltma İşleçleri: ++ ve --

## <a name="syntax"></a>Sözdizimi

```
postfix-expression ++
postfix-expression --
```

## <a name="remarks"></a>Açıklamalar

C++ önek ve sonek artırma ve azaltma işleçleri sağlar; bu bölümde yalnızca sonek artırma ve azaltma işleçleri açıklanmaktadır. (Daha fazla bilgi için bkz. [önek artırma ve azaltma işleçleri](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md).) İkisi arasındaki fark, sonek gösteriminde, işleç *sonek ifadesinden*sonra görünür, ancak ön ek gösterimde, işleç ifadeden önce görünür *.* Aşağıdaki örnekte, bir sonek artırma işleci gösterilmektedir:

```cpp
i++;
```

Sonek artışı işlecini () uygulamanın etkisi, **++** işlenenin değerinin uygun türde bir birim artmasıdır. Benzer şekilde, sonek azaltma işlecini () uygulamanın etkisi, **--** işlenenin değerinin uygun türde bir birimle azaltılmadır.

Bir sonek artışı veya azaltma ifadesi ilgili işlecin uygulamadan *önce* ifadenin değerini değerlendirdiğini unutmayın. Artış veya azaltma işlemi, işlenen *hesaplandıktan sonra* gerçekleşir. Bu sorun, yalnızca sonek artırma veya azaltma işlevi daha büyük bir ifadenin bağlamında gerçekleştiğinde ortaya çıkar.

Bir sonek işleci bir işlevin bağımsız değişkenine uygulandığında, bağımsız değişkenin değerinin işleve geçirilmeden önce artırılması veya azaltılması garanti edilmez.  Daha fazla bilgi için C++ standardındaki 1.9.17 bölümüne bakın.

Sonek artışı işlecinin türü bir nesne dizisinin bir işaretçisine uygulanması **`long`** aslında işaretçinin iç gösterimine dört ekler. Bu davranış, daha önce dizinin *n*. öğesine başvuruda bulunan işaretçinin (*n*+ 1) TH öğesine başvurmasına neden olur.

Sonek artışının ve sonek azaltma işleçlerinin işlenenleri, **`const`** aritmetik veya işaretçi türünde bir l-değerleri değiştirilebilir olmalıdır. Sonucun türü, *sonek ifadesi*ile aynıdır, ancak artık bir l değeri değildir.

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir): bir sonek artışı veya azaltma işlecinin işleneni türünde olamaz **`bool`** .

Aşağıdaki kod sonek artırma işlecini gösterir:

```cpp
// expre_Postfix_Increment_and_Decrement_Operators.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
   int i = 10;
   cout << i++ << endl;
   cout << i << endl;
}
```

Numaralandırılmış türler üzerinde postincrement ve postdecrement işlemleri desteklenmez:

```cpp
enum Compass { North, South, East, West );
Compass myCompass;
for( myCompass = North; myCompass != West; myCompass++ ) // Error
```

## <a name="see-also"></a>Ayrıca bkz.

[Sonek Ifadeleri](../cpp/postfix-expressions.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Sonek artışı ve azaltma Işleçleri](../c-language/c-postfix-increment-and-decrement-operators.md)
