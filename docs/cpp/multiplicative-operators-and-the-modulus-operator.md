---
title: Çarpan İşleçleri ve Modulus İşleci
ms.date: 11/04/2016
f1_keywords:
- '%'
- /
helpviewer_keywords:
- operators [C++], multiplicative
- arithmetic operators [C++], multiplicative operators
- modulus operator [C++]
- '* operator'
- division operator [C++], multiplicative operators
- '% operator'
- multiplication operator [C++], multiplicative operators
- multiplicative operators [C++]
- division operator
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
ms.openlocfilehash: 791f18793b49f7d3a986c3271fddef3acef33062
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367921"
---
# <a name="multiplicative-operators-and-the-modulus-operator"></a>Çarpan İşleçleri ve Modulus İşleci

## <a name="syntax"></a>Sözdizimi

```
expression * expression
expression / expression
expression % expression
```

## <a name="remarks"></a>Açıklamalar

Çarpma işleçleri şunlardır:

- Çarpma (<strong>\*</strong>)

- Tümen**/**( )

- Modül (bölümden kalan)**%**( )

Bu ikili işleçlerde soldan sağa ilişkilendirilebilirlik vardır.

Çarpma işleçleri aritmetik türlerin işlenenlerini alır. Modül işleci**%**( ) operands integral tip olmalıdır daha sıkı bir gereksinime sahiptir. (Kayan nokta bölümünün geri kalanını almak için çalışma zamanı işlevini kullanın, [fmod](../c-runtime-library/reference/fmod-fmodf.md).) [Standart Dönüşümler](standard-conversions.md) kapsamındaki dönüşümler operandlara uygulanır ve sonuç dönüştürülmüş türe göre dir.

Çarpma işleci, birinci işlenenin ikinci işlenen ile çarpımının sonucu verir.

Bölme işleci, birinci işlenenin ikinci işlenene bölünmesinin sonucu verir.

Modül operatörü, *e1'in* ilk operand olduğu ve *e2'nin* ikinci olduğu aşağıdaki ifadeile verilen geri kalanı \* verir: *e1* - (*e1* / *e2*) *e2*, her iki operandun da integral tipleri olduğu.

Bir bölüm ya da mod ifadesinde 0'a bölme tanımlı değildir ve bir çalışma zamanı hatasına neden olur. Bu nedenle, aşağıdaki ifadeler tanımlanmamış, hatalı sonuçlar oluşturur:

```cpp
i % 0
f / 0.0
```

Çarpma, bölme ya da mod ifadelerinde her iki işlenen de aynı işarete sahipse, sonuç pozitif olur. Aksi halde, sonuç negatif olur. Bir mod işleminin işaretinin sonucu uygulama tarafından tanımlanır.

> [!NOTE]
> Çarpma işleçleri tarafından gerçekleştirilen dönüştürmeler taşma veya yetersiz kalma koşulları sağlamadığından, çarpma işleminin sonucu dönüştürme sonrası işlenenlerin türünde gösterilmezse bilgiler kaybolabilir.

**Microsoft'a Özgü**

Microsoft C++'da, bir mod ifadesinin sonucu her zaman birinci işlenenin işaretiyle aynıdır.

**END Microsoft Özel**

Hesaplanan iki tamsayı bölümünü kesin değilse ve yalnızca tek bir işlenen negatif ise, sonuç bölme işleminin vereceği tam değerden daha küçük en büyük tamsayı (büyüklükte, işaret dikkate alınmadığında) olur. Örneğin, -11 / 3'ün hesaplanan değeri -3,66666666'dır. Bu integral bölünmenin sonucu -3'tür.

Çarpan işleçleri arasındaki ilişki kimlik (*e1* / *e2*) \* *e2* + *e1* % *e2* == *e1*tarafından verilir.

## <a name="example"></a>Örnek

Aşağıdaki program çarpma işleçlerini gösterir. Her iki operands bölünme önce tipi `10 / 3` **float** böylece kesilme önlemek için **float** yazmak için açıkça döküm gerektiğini unutmayın.

```cpp
// expre_Multiplicative_Operators.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
int main() {
   int x = 3, y = 6, z = 10;
   cout  << "3 * 6 is " << x * y << endl
         << "6 / 3 is " << y / x << endl
         << "10 % 3 is " << z % x << endl
         << "10 / 3 is " << (float) z / x << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[İkili İşleçli İfadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Çarpan operatörler](../c-language/c-multiplicative-operators.md)
