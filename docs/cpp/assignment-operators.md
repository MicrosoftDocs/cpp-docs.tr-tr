---
title: Atama İşleçleri
ms.date: 03/05/2018
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
ms.openlocfilehash: d435ea051610f9ffa496f41f364ffc1c81694b61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617405"
---
# <a name="assignment-operators"></a>Atama İşleçleri

## <a name="syntax"></a>Sözdizimi

*ifade* *atama işleci* *ifadesi*

*atama işleci* : biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>= * =, / = % =, +=-= \< \<= >> = & = ^ =   \|=</strong>

## <a name="remarks"></a>Açıklamalar

Atama işleçleri, sol işlenen tarafından belirlenen nesnede bir değer depolar. İki tür arama işlemi vardır:

1. *Basit atama*, ilk işlenen tarafından belirtilen nesnede ikinci işlenenin değerini depolandığı içinde.

1. *bileşik atama*, içinde bir aritmetik, kaydırma veya bit düzeyinde işlem gerçekleştirilir sonucu depolamadan önce.

Aşağıdaki tabloda, = işleci hariç tüm atama işleçleri birleşik atama işleçleridir.

### <a name="assignment-operators"></a>Atama İşleçleri

|İşleç|Açıklama|
|--------------|-------------|
|**=**|Birinci işlenen (basit atama) tarafından belirtilen nesnede ikinci işlenenin değerini depolar.|
|**\*=**|Birinci işlenenin değeriyle ikinci işlenenin değerini çarpar; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|
|**/=**|Birinci işlenenin değerini ikinci işlenenin değerine böler; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|
|**%=**|İkinci işlenenin değeri tarafından belirtilen birinci işlenenin modüllerini alır; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|
|**+=**|İkinci işlenenin değerine birinci işlenenin değerini ekler; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|
|**-=**|İkinci işlenenin değerinden ilk işlenenin değerini çıkarır; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|
|**<\<=**|Birinci işlenenin değerini ikinci işlenenin değeri tarafından belirtilen bit sayısının soluna kaydırır; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|
|**>>=**|Birinci işlenenin değerini ikinci işlenenin değeri tarafından belirtilen bit sayısının sağına kaydırır; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|
|**&=**|Birinci ve ikinci işlenenden bit seviyesinde VE elde eder; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|
|**^=**|Birinci ve ikinci işlenenden bit seviyesinde dışlamalı VEYA elde eder; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|
|**\|=**|Birinci ve ikinci işlenenden bit seviyesinde kapsamalı VEYA elde eder; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|

**İşleç Anahtar Sözcükleri**

Bileşik atama işleçlerinden üçünün metin eşdeğerleri vardır. Bunlar:

|İşleç|Eşdeğer|
|--------------|----------------|
|**&=**|`and_eq`|
|**\|=**|`or_eq`|
|**^=**|`xor_eq`|

Programlarınızda bu anahtar sözcüklere erişmenin iki yolu vardır: üstbilgi dosyasını dahil `iso646.h`, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırakma) derleyici seçeneği.

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

Basit atama işleci (**=**) ilk işlenen tarafından belirtilen nesnede depolanan ikinci işlenenin değerini neden olur. Aritmetik türde iki nesne varsa, sağ işlenen değer depolama önce soldaki türüne dönüştürülür.

Nesnelerin **const** ve **geçici** türleri yalnızca türlere, l-değerler için atanabilir **geçici** veya hiçbiri olan **const** ya da **geçici**.

Atama (yapı, birleşim ve sınıf türleri) sınıf türünden nesnelere adlı bir işlev tarafından gerçekleştirilen `operator=`. Bu işleç işlevini varsayılan davranışı, bit düzeyinde kopyalama işlemini gerçekleştirmek için değildir; Ancak, bu davranışı, aşırı yüklenmiş işleçler kullanılarak değiştirilebilir. Bkz: [işleci aşırı yüklemesi](../cpp/operator-overloading.md) daha fazla bilgi için. Ayrıca, sınıf türleri olabilir *kopyalama ataması* ve *atama taşıma* işleçleri. Daha fazla bilgi için [oluşturucuları kopyalama ve atama işleçlerini kopyalayın](copy-constructors-and-copy-assignment-operators-cpp.md) ve [taşıma oluşturucuları ve taşıma atama işleçleri](move-constructors-and-move-assignment-operators-cpp.md).

Belirli bir taban sınıftan tüm kesin bir şekilde türetilen sınıfın bir nesnesi, temel sınıfın bir nesneye atanabilir. Geriye doğru olmadığı için örtük bir dönüştürme temel sınıfından türetilmiş bir sınıf true değil, ancak değil, temel sınıf için türetilmiş sınıf. Örneğin:

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

Atama başvurunun işaret ettiği nesnenin yapılmış olan başvuru türleri için atamaları bilgisayarmış gibi.

Sınıf türü nesneler için atama başlatmadan farklıdır. Farklı atama ve başlatma göstermek için olması, koda göz önünde bulundurun

```cpp
UserType1 A;
UserType2 B = A;
```

Yukarıdaki kod, bir başlatıcı gösterir. için oluşturucu çağrısı `UserType2` türünde bir bağımsız değişken almayan `UserType1`. Verilen kod

```cpp
UserType1 A;
UserType2 B;

B = A;
```

atama ifadesi

```cpp
B = A;
```

Aşağıdaki etkileri biri olabilir:

- İşlev çağrısı `operator=` için `UserType2`, sağlanan `operator=` ile sağlanan bir `UserType1` bağımsız değişken.

- Açık dönüştürme işlevini çağırın `UserType1::operator UserType2`, böyle bir işlevi varsa.

- Bir oluşturucu çağrı `UserType2::UserType2`, bu tür bir oluşturucuya alan var. sağlanan bir `UserType1` bağımsız değişken ve sonucu kopyalar.

## <a name="compound-assignment"></a>Bileşik atama

Tablosunda gösterilen bileşik atama işleçleri [atama işleçleri](#assignment-operators), biçiminde belirtilen *e1* *op*= *e2*burada *e1* olmayan değiştirilebilir bir l-değeri olan **const** türü ve *e2* aşağıdakilerden biridir:

- Bir aritmetik tür

- Bir işaretçi ise *op* olduğu **+** veya **-**

*E1* *op*= *e2* form davranışını olarak *e1* **=** *e1* *op* *e2*, ancak *e1* yalnızca bir kez değerlendirilir.

Numaralandırılmış bir türe yapılan bileşik atama bir hata iletisi oluşturur. Sol işlenen bir işaretçi türü ise, sağ işlenen bir işaretçi türünde olmalıdır veya 0 olarak değerlendirilen bir sabit bir ifade olması gerekir. Sol işlenen bir tamsayı türü ise, sağ işlenen bir işaretçi türü olmamalıdır.

## <a name="result-of-assignment-operators"></a>Atama İşleçleri sonucu

Atama İşleçleri atamasından sonra sol işlenen tarafından belirtilen nesnenin değerini döndürür. Sonuç türü, sol işlenenin türüdür. Bir atama ifadesinin sonucu her zaman bir l değeridir. Bu işleçler, sağdan sola birleşme özelliği içindedir. Sol işleneni değiştirilebilir bir l-değeri olmalıdır.

ANSI C, bir atama ifadesinin sonucu bir l değeri değil. Bu nedenle, yasal C++ ifadesi `(a += b) += c` C'de geçersizdir

## <a name="see-also"></a>Ayrıca bkz.

[İkili İşleçli İfadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Atama İşleçleri](../c-language/c-assignment-operators.md)
