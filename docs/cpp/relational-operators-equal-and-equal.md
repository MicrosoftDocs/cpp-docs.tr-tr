---
title: 'İlişkisel Işleçler: &lt;, &gt;, &lt;= ve &gt;='
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
ms.openlocfilehash: 38e05b78d334ca690d9523797f7ca1813834c5d3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179126"
---
# <a name="relational-operators-lt-gt-lt-and-gt"></a>İlişkisel Işleçler: &lt;, &gt;, &lt;= ve &gt;=

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

- Büyük veya eşittir ( **>=** )

İlişkisel işleçler soldan sağa ilişkilendiriledir. Her iki ilişkisel işleç işleneni de aritmetik veya işaretçi türünde olmalıdır. Bunlar **bool**türünde değerler verir. İfadedeki ilişki false olduğunda döndürülen değer **false** 'dur (0). Aksi takdirde döndürülen değer **true** 'dur (1).

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

Önceki örnekteki ifadeler parantez içine alınmalıdır, çünkü Stream ekleme işleci ( **<<** ), ilişkisel işleçlerden daha yüksek önceliğe sahiptir. Bu nedenle, parantezler olmadan ilk ifade şöyle değerlendirilir:

```cpp
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");
```

[Standart dönüştürmelerde](standard-conversions.md) ele alınan Olağan aritmetik dönüştürmeler aritmetik türlerin işlenenlerine uygulanır.

## <a name="comparing-pointers"></a>İşaretçileri karşılaştırma

Aynı türden nesnelerin iki işaretçisi karşılaştırıldığı zaman, sonuç programın adres alanında işaret edilen nesnelerin konumuyla belirlenir. İşaretçiler Ayrıca 0 veya `void *`türünde bir işaretçiye değerlendirilen bir sabit ifadeyle karşılaştırılabilir. `void *`türünde bir işaretçiye yönelik bir işaretçi karşılaştırması yapılırsa, diğer işaretçi örtülü olarak `void *`türüne dönüştürülür. Ardından karşılaştırma yapılır.

Farklı türlerin iki işaretçisi şu durumlar dışında karşılaştırılamaz:

- Bir tür, diğer türden türetilmiş bir sınıf türüdür.

- İşaretçilerden en az biri açık olarak `void *`türüne dönüştürüldü (atama). (Diğer işaretçi dönüştürme için `void *` türüne örtülü olarak dönüştürülür.)

Aynı nesneye işaret eden aynı türden iki işaretçinin eşit olarak karşılaştırılacağı garanti edilir. Bir nesnenin statik olmayan üyelerine yönelik iki işaretçi karşılaştırılabiliyorsanız, aşağıdaki kurallar geçerlidir:

- Sınıf türü bir **birleşim**değilse ve iki üye, **genel**, **korumalı**veya **özel**gibi bir *erişim belirticisi*tarafından ayrılmadığında, son olarak belirtilen üyenin işaretçisi, daha önce belirtilen üyenin işaretçisinden daha büyük bir değer karşılaştırır.

- İki üye bir *erişim belirticisi*ile ayrılırsa, sonuçlar tanımsızdır.

- Sınıf türü bir **Union**ise, bu **birleşim** karşılaştırıldığı farklı veri üyelerine işaretçiler eşittir.

İki işaretçi, aynı dizideki öğeleri veya dizi sonunun ötesinde olan öğeye işaret ederseniz, daha yüksek alt indisi olan nesneye yönelik işaretçi daha yüksek bir şekilde karşılaştırılır. İşaretçilerin karşılaştırılması, yalnızca işaretçiler aynı dizideki nesnelere ya da dizinin sonundan geçmiş bir konuma başvurduğunuzda geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[İkili İşleçli İfadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C İlişkisel ve Eşitlik İşleçleri](../c-language/c-relational-and-equality-operators.md)
