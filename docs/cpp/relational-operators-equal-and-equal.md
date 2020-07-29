---
title: 'İlişkisel işleçler: &lt; , &gt; , &lt; = ve&gt;='
ms.date: 11/04/2016
f1_keywords:
- <
- '>'
helpviewer_keywords:
- '> operator'
- less than operator
- relational operators [C++], syntax
- '>= operator'
- greater than or equal to operators [C++]
- greater than operators [C++]
- < operator
- less than or equal to operator
- <= operator
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
ms.openlocfilehash: 81421a135059b8804955d472365ebef9802d3210
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227120"
---
# <a name="relational-operators-lt-gt-lt-and-gt"></a>İlişkisel işleçler: &lt; , &gt; , &lt; = ve&gt;=

## <a name="syntax"></a>Sözdizimi

```
expression < expression
expression > expression
expression <= expression
expression >= expression
```

## <a name="remarks"></a>Açıklamalar

İkili ilişkisel işleçler aşağıdaki ilişkileri belirlenir:

- Küçüktür ( **\<** )

- Büyüktür ( **>** )

- Küçüktür veya eşittir ( **\<=** )

- Büyüktür veya eşittir ( **>=** )

İlişkisel işleçler soldan sağa ilişkilendiriledir. Her iki ilişkisel işleç işleneni de aritmetik veya işaretçi türünde olmalıdır. Bunlar türünde değer elde ederler **`bool`** . **`false`** İfadedeki ilişki false ise döndürülen değer (0), aksi takdirde döndürülen değer **`true`** (1).

## <a name="example"></a>Örnek

```cpp
// expre_Relational_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   cout  << "The true expression 3 > 2 yields: "
         << (3 > 2) << endl
         << "The false expression 20 < 10 yields: "
         << (20 < 10) << endl;
}
```

Önceki örnekteki ifadelerin parantez içine alınması gerekir, çünkü Stream ekleme işleci ( **<<** ), ilişkisel işleçlerden daha yüksek önceliğe sahiptir. Bu nedenle, parantezler olmadan ilk ifade şöyle değerlendirilir:

```cpp
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");
```

[Standart dönüştürmelerde](standard-conversions.md) ele alınan Olağan aritmetik dönüştürmeler aritmetik türlerin işlenenlerine uygulanır.

## <a name="comparing-pointers"></a>İşaretçileri karşılaştırma

Aynı türden nesnelerin iki işaretçisi karşılaştırıldığı zaman, sonuç programın adres alanında işaret edilen nesnelerin konumuyla belirlenir. İşaretçiler Ayrıca, 0 veya türü bir işaretçiye değerlendirilen bir sabit ifadeyle da karşılaştırılabilir `void *` . Bir işaretçi karşılaştırma türü işaretçisine karşı yapılırsa `void *` , diğer işaretçi örtülü olarak türüne dönüştürülür `void *` . Ardından karşılaştırma yapılır.

Farklı türlerin iki işaretçisi şu durumlar dışında karşılaştırılamaz:

- Bir tür, diğer türden türetilmiş bir sınıf türüdür.

- İşaretçilerden en az biri açık olarak türe dönüştürüldü (atama) `void *` . (Diğer işaretçi, dönüştürme için örtük olarak türüne dönüştürülür `void *` .)

Aynı nesneye işaret eden aynı türden iki işaretçinin eşit olarak karşılaştırılacağı garanti edilir. Bir nesnenin statik olmayan üyelerine yönelik iki işaretçi karşılaştırılabiliyorsanız, aşağıdaki kurallar geçerlidir:

- Sınıf türü bir değilse **`union`** ve iki üye, veya gibi bir *erişim belirticisi*tarafından ayrılmadığında, **`public`** son olarak **`protected`** **`private`** belirtilen üyenin işaretçisi, daha önce belirtilen üyenin işaretçisinden daha büyük bir değer karşılaştırır.

- İki üye bir *erişim belirticisi*ile ayrılırsa, sonuçlar tanımsızdır.

- Sınıf türü bir ise **`union`** , bu karşılaştırma içindeki farklı veri üyelerine işaretçiler **`union`** eşittir.

İki işaretçi, aynı dizideki öğeleri veya dizi sonunun ötesinde olan öğeye işaret ederseniz, daha yüksek alt indisi olan nesneye yönelik işaretçi daha yüksek bir şekilde karşılaştırılır. İşaretçilerin karşılaştırılması, yalnızca işaretçiler aynı dizideki nesnelere ya da dizinin sonundan geçmiş bir konuma başvurduğunuzda geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Ikili Işleçlere sahip ifadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Ilişkisel ve eşitlik Işleçleri](../c-language/c-relational-and-equality-operators.md)
