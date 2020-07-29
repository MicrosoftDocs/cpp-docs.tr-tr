---
title: Atama işleçleri
description: C++ standart dil atama işleçleri sözdizimi ve kullanımı.
ms.date: 07/24/2020
f1_keywords:
- =
- '*='
- /=
- '%='
- +=
- -=
- <<=
- '>>='
- '&='
- ^=
- '|='
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], C++
- '&= operator'
- ^= operator
- += operator
- '>>= operator'
- '|= operator'
- operator>>=
- '*= operator'
- '%= operator'
- ^= operator
- operator >>=
- = operator
- -= operator
- /= operator
- <<= operator
ms.assetid: b028cf35-2ff1-4f14-9027-fd53ebec8aa0
ms.openlocfilehash: 91346d06c6fab4f3cd83c5318c88e738daf8d249
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229226"
---
# <a name="assignment-operators"></a>Atama işleçleri

## <a name="syntax"></a>Sözdizimi

*ifade* *atama-işleç* *ifadesi*

*atama-işleç*: aşağıdakilerden biri<br/>
&emsp;**`=`**&emsp;**`*=`**&emsp;**`/=`**&emsp;**`%=`**&emsp;**`+=`**&emsp;**`-=`**&emsp;**`<<=`**&emsp;**`>>=`**&emsp;**`&=`**&emsp;**`^=`**&emsp;**`|=`**

## <a name="remarks"></a>Açıklamalar

Atama işleçleri, sol işlenen tarafından belirtilen nesnede bir değer depolar. İki tür atama işlemi vardır:

- ikinci işlenenin değerinin ilk işlenen tarafından belirtilen nesnede depolandığı *basit atama*.

- sonucu depolamadan önce aritmetik, kaydırma veya bit düzeyinde işlem gerçekleştirilen *bileşik atama*.

Aşağıdaki tabloda işleç hariç tüm atama işleçleri **`=`** bileşik atama işleçleridir.

### <a name="assignment-operators-table"></a>Atama işleçleri tablosu

| İşleç | Anlamı |
|--|--|
| **`=`** | Birinci işlenen (basit atama) tarafından belirtilen nesnede ikinci işlenenin değerini depolar. |
| **`*=`** | Birinci işlenenin değeriyle ikinci işlenenin değerini çarpar; sonucu ilk işlenen tarafından belirtilen nesnede depolar. |
| **`/=`** | Birinci işlenenin değerini ikinci işlenenin değerine böler; sonucu ilk işlenen tarafından belirtilen nesnede depolar. |
| **`%=`** | İkinci işlenenin değeri tarafından belirtilen birinci işlenenin modüllerini alır; sonucu ilk işlenen tarafından belirtilen nesnede depolar. |
| **`+=`** | İkinci işlenenin değerine birinci işlenenin değerini ekler; sonucu ilk işlenen tarafından belirtilen nesnede depolar. |
| **`-=`** | İkinci işlenenin değerinden ilk işlenenin değerini çıkarır; sonucu ilk işlenen tarafından belirtilen nesnede depolar. |
| **`<<=`** | Birinci işlenenin değerini ikinci işlenenin değeri tarafından belirtilen bit sayısının soluna kaydırır; sonucu ilk işlenen tarafından belirtilen nesnede depolar. |
| **`>>=`** | Birinci işlenenin değerini ikinci işlenenin değeri tarafından belirtilen bit sayısının sağına kaydırır; sonucu ilk işlenen tarafından belirtilen nesnede depolar. |
| **`&=`** | Birinci ve ikinci işlenenden bit seviyesinde VE elde eder; sonucu ilk işlenen tarafından belirtilen nesnede depolar. |
| **`^=`** | Birinci ve ikinci işlenenden bit seviyesinde dışlamalı VEYA elde eder; sonucu ilk işlenen tarafından belirtilen nesnede depolar. |
| **`|=`** | Birinci ve ikinci işlenenden bit seviyesinde kapsamalı VEYA elde eder; sonucu ilk işlenen tarafından belirtilen nesnede depolar. |

### <a name="operator-keywords"></a>İşleç anahtar sözcükleri

Bileşik atama işleçlerinin üçünün anahtar sözcük eşdeğerleri vardır. Bunlar:

| İşleç | Eşdeğer |
|--|--|
| **`&=`** | **`and_eq`** |
| **`|=`** | **`or_eq`** |
| **`^=`** | **`xor_eq`** |

C++, bu işleç anahtar sözcüklerini bileşik atama işleçleri için alternatif yazım olarak belirtir. C 'de alternatif yazımlar üst bilgide makrolar olarak sağlanır \<iso646.h> . C++ ' da, diğer yazımlar anahtar kelimelerdir; \<iso646.h>C++ eşdeğeri veya kullanımı \<ciso646> kullanım dışıdır. Microsoft C++ ' da, [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) alternatif yazımı etkinleştirmek için veya derleyici seçeneği gereklidir.

## <a name="example"></a>Örnek

```cpp
// expre_Assignment_Operators.cpp
// compile with: /EHsc
// Demonstrate assignment operators
#include <iostream>
using namespace std;
int main() {
   int a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555;

   a += b;      // a is 9
   b %= a;      // b is 6
   c >>= 1;      // c is 5
   d |= e;      // Bitwise--d is 0xFFFF

   cout  << "a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555" << endl
         << "a += b yields " << a << endl
         << "b %= a yields " << b << endl
         << "c >>= 1 yields " << c << endl
         << "d |= e yields " << hex << d << endl;
}
```

## <a name="simple-assignment"></a>Basit atama

Basit atama işleci ( **`=`** ) ikinci işlenenin değerinin ilk işlenen tarafından belirtilen nesnede depolanmasına neden olur. Her iki nesne de aritmetik türtürsa, değeri depolamadan önce sağ işlenen, sol taraftaki türe dönüştürülür.

**`const`** Ve türlerinin nesneleri **`volatile`** yalnızca, veya olmayan türlerin l değerlerine atanabilir **`volatile`** **`const`** **`volatile`** .

Sınıf türü ( **`struct`** , **`union`** ve **`class`** türleri) nesnelerine atama adlı bir işlev tarafından gerçekleştirilir `operator=` . Bu işleç işlevinin varsayılan davranışı bit düzeyinde bir kopya gerçekleştirmetir; Ancak, bu davranış aşırı yüklenmiş işleçler kullanılarak değiştirilebilir. Daha fazla bilgi için bkz. [operatör aşırı yüklemesi](../cpp/operator-overloading.md). Sınıf türlerinde Ayrıca *kopyalama atama* ve *taşıma atama* işleçleri de bulunabilir. Daha fazla bilgi için bkz. [kopya oluşturucuları ve kopya atama işleçleri](copy-constructors-and-copy-assignment-operators-cpp.md) ve [Taşıma Oluşturucuları ve taşıma atama işleçleri](move-constructors-and-move-assignment-operators-cpp.md).

Belirli bir taban sınıftan herhangi bir belirsiz türetilmiş sınıfın nesnesi, temel sınıfın bir nesnesine atanabilir. Türetilmiş sınıftan taban sınıfa örtük bir dönüştürme olduğundan, tersi doğru değildir, ancak temel sınıftan türetilmiş sınıfa değil. Örnek:

```cpp
// expre_SimpleAssignment.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
class ABase
{
public:
    ABase() { cout << "constructing ABase\n"; }
};

class ADerived : public ABase
{
public:
    ADerived() { cout << "constructing ADerived\n"; }
};

int main()
{
    ABase aBase;
    ADerived aDerived;

    aBase = aDerived; // OK
    aDerived = aBase; // C2679
}
```

Başvuru türlerine atamalar, atamanın başvuru noktası olan nesneye yapılmış gibi davranır.

Sınıf türü nesneler için atama başlangıçtan farklıdır. Farklı atama ve başlatmanın nasıl kullanılabileceğini göstermek için, kodu değerlendirin

```cpp
UserType1 A;
UserType2 B = A;
```

Yukarıdaki kod bir başlatıcı gösterir; `UserType2`Bu, öğesinin türünde bir bağımsız değişken alan oluşturucusunu çağırır `UserType1` . Kod verildiğinde

```cpp
UserType1 A;
UserType2 B;

B = A;
```

atama ekstresi

```cpp
B = A;
```

Aşağıdaki etkilerden birine sahip olabilir:

- İçin işlevini çağırın `operator=` `UserType2` , belirtilen `operator=` bir `UserType1` bağımsız değişkenle sağlanır.

- `UserType1::operator UserType2`Böyle bir işlev varsa, açık dönüştürme işlevini çağırın.

- `UserType2::UserType2` `UserType1` Bağımsız değişken alan ve sonucu kopyalayan bir Oluşturucu varsa, bu tür bir Oluşturucu çağırın.

## <a name="compound-assignment"></a>Bileşik atama

Bileşik atama işleçleri, [atama işleçleri tablosunda](#assignment-operators-table)gösterilir. Bu işleçler, E1 'ın *e1* *op* =  *e2*değiştirilemeyen *e1* bir **`const`** l-Value ve *E2* olduğu biçimde E1 op E2 biçimindedir.

- aritmetik tür

- bir işaretçi, veya *işleci* ise **`+`****`-`**

*E1* *op* =  *E2* formu *E1* **`=`** *E1* *op* *E2*olarak davranır, ancak *E1* yalnızca bir kez değerlendirilir.

Numaralandırılmış bir türe yapılan bileşik atama bir hata iletisi oluşturur. Sol işlenen bir işaretçi türü ise, sağ işlenen bir işaretçi türünde olmalıdır veya 0 olarak değerlendirilen bir sabit ifade olmalıdır. Sol işlenen bir integral türünde olduğunda, sağ işlenen bir işaretçi türü olmamalıdır.

## <a name="result-of-assignment-operators"></a>Atama işleçleri sonucu

Atama işleçleri, atamadan sonra sol işlenen tarafından belirtilen nesnenin değerini döndürür. Sonuç türü, sol işlenenin türüdür. Atama ifadesinin sonucu her zaman bir l değeridir. Bu operatörlerin sağdan sola ilişkilendirilebilirliği vardır. Sol işlenen, değiştirilebilir bir l değeri olmalıdır.

ANSI C 'de, atama ifadesinin sonucu bir l değeri değildir. Bu, C 'de yasal C++ ifadesine `(a += b) += c` izin verilmediği anlamına gelir.

## <a name="see-also"></a>Ayrıca bkz.

[İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C atama işleçleri](../c-language/c-assignment-operators.md)
