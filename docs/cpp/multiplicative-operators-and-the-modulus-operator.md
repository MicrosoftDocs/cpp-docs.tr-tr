---
description: 'Daha fazla bilgi edinin: Çoğulereptive Işleçleri ve mod Işleci'
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
ms.openlocfilehash: e3e3e3823abb255922bf31be90b4a116fb100efe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313872"
---
# <a name="multiplicative-operators-and-the-modulus-operator"></a>Çarpan İşleçleri ve Modulus İşleci

## <a name="syntax"></a>Syntax

```
expression * expression
expression / expression
expression % expression
```

## <a name="remarks"></a>Açıklamalar

Çarpma işleçleri şunlardır:

- Çarpma ( <strong>\*</strong> )

- Bölüm ( **/** )

- Mod (bölmenin geri kalanı) ( **%** )

Bu ikili işleçlerde soldan sağa ilişkilendirilebilirlik vardır.

Çarpma işleçleri aritmetik türlerin işlenenlerini alır. Mod işleci ( **%** ), işlenenlerinin integral türünde olması gereken daha katı bir gereksinime sahiptir. (Kayan nokta bölümünün kalanını almak için, çalışma zamanı işlevini kullanın, [fmod](../c-runtime-library/reference/fmod-fmodf.md).) [Standart dönüştürmelerde](standard-conversions.md) kapsanan dönüştürmeler işlenenlere uygulanır ve sonuç, dönüştürülmüş tür olur.

Çarpma işleci, birinci işlenenin ikinci işlenen ile çarpımının sonucu verir.

Bölme işleci, birinci işlenenin ikinci işlenene bölünmesinin sonucu verir.

Mod işleci, aşağıdaki ifade tarafından verilen geri kalanı verir, burada *E1* ilk işlenen ve *E2* ikinci: *E1* -(*E1*  /  *E2*) \* *E2*, burada her iki işlenen de İntegral türlerdir.

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

**SON Microsoft 'a özgü**

Hesaplanan iki tamsayı bölümünü kesin değilse ve yalnızca tek bir işlenen negatif ise, sonuç bölme işleminin vereceği tam değerden daha küçük en büyük tamsayı (büyüklükte, işaret dikkate alınmadığında) olur. Örneğin,-11/3 hesaplanan değeri-3,666666666 ' dir. Bu integral bölümünün sonucu-3 ' tir.

Çarpma işleçleri arasındaki ilişki kimlik (*E1*  /  *E2*) \* *E2*  +  *E1*  %  *E2*  ==  *E1* tarafından verilir.

## <a name="example"></a>Örnek

Aşağıdaki program çarpma işleçlerini gösterir. `10 / 3` **`float`** Her iki işlenenin de bölme öncesinde türü olması adına, kesilmemek için öğesinin her iki işleneninin açıkça türe dönüştürülmesi gerektiğini unutmayın **`float`** .

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

[Ikili Işleçlere sahip ifadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C çarpma Işleçleri](../c-language/c-multiplicative-operators.md)
