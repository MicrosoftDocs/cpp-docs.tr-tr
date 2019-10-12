---
title: 'Koşullu Işleç: &quest;:'
ms.date: 11/04/2016
f1_keywords:
- '?:'
- '?'
helpviewer_keywords:
- conditional operators [C++]
- '? : operator'
ms.assetid: 88643ee8-7100-4f86-880a-705ec22b6271
ms.openlocfilehash: 0a66b82682f90345518a2d520945e3aff1f78f89
ms.sourcegitcommit: 170f5de63b0fec8e38c252b6afdc08343f4243a6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2019
ms.locfileid: "72276811"
---
# <a name="conditional-operator-quest-"></a>Koşullu Işleç: &quest;:

## <a name="syntax"></a>Sözdizimi

```
expression ? expression : expression
```

## <a name="remarks"></a>Açıklamalar

Koşullu işleç ( **?:** ) üçlü bir işleçtir (üç işlenen alır). Koşullu işleç aşağıdaki gibi çalışmaktadır:

- İlk işlenen örtük olarak **bool**değerine dönüştürülür. Değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlanır.

- İlk işlenen **true** (1) olarak değerlendirilirse, ikinci işlenen değerlendirilir.

- İlk işlenen **yanlış** (0) olarak değerlendirilirse, üçüncü işlenen değerlendirilir.

Koşullu işlecin sonucu, ikinci veya üçüncü bir işlenenin değerlendirildiği bir sonucudur. Bir koşullu ifadede yalnızca son iki işlenenden yalnızca biri değerlendirilir.

Koşullu ifadeler sağdan sola ilişkilendiriledir. İlk işlenen integral veya işaretçi türünde olmalıdır. Aşağıdaki kurallar ikinci ve üçüncü işlenenler için geçerlidir:

- Her iki işlenen de aynı türde ise, sonuç o tür olur.

- Her iki işlenen de aritmetik veya sabit listesi türlerindiyse, normal aritmetik dönüştürmeler ( [Standart dönüşümlerde](standard-conversions.md)ele alınmıştır), bunları ortak bir türe dönüştürmek için gerçekleştirilir.

- Her iki işlenen de işaretçi türlerisiyse veya biri işaretçi türü ise ve diğeri 0 olarak değerlendirilen bir sabit ifadeyse, bunları ortak bir türe dönüştürmek için işaretçi dönüşümleri gerçekleştirilir.

- Her iki işlenen de başvuru türlerindiyse, bunları ortak bir türe dönüştürmek için başvuru dönüştürmeleri yapılır.

- Her iki işlenen de void türünde ise, ortak tür void türüdür.

- Her iki işlenen de aynı kullanıcı tanımlı türde ise, ortak tür bu türdür.

- İşlenenler farklı türlere sahipse ve işlenenlerinden en az birinde Kullanıcı tanımlı tür varsa, ortak türü belirlemede dil kuralları kullanılır. (Aşağıdaki uyarıya bakın.)

Önceki listede olmayan ikinci ve üçüncü işlenenlerin birleşimleri geçersizdir. Sonucun türü ortak türdür ve ikinci ve üçüncü işlenenleri aynı türde ve her ikisi de l-Values olduğunda bir l değeri olur.

> [!WARNING]
>  İkinci ve üçüncü işlenenlerinin türleri özdeş değilse, C++ standart olarak belirtilen şekilde, karmaşık tür dönüştürme kuralları çağrılır. Bu dönüşümler, geçici nesnelerin oluşturulması ve yok edilmesi gibi beklenmeyen davranışlara neden olabilir. Bu nedenle, Kullanıcı tanımlı türleri koşullu işleçle (1) işlenen olarak kullanmaktan kaçının veya (2) Kullanıcı tanımlı türleri kullanıyorsanız, her işleneni açıkça ortak bir türe atamalısınız.

## <a name="example"></a>Örnek

```cpp
// expre_Expressions_with_the_Conditional_Operator.cpp
// compile with: /EHsc
// Demonstrate conditional operator
#include <iostream>
using namespace std;
int main() {
   int i = 1, j = 2;
   cout << ( i > j ? i : j ) << " is greater." << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++Yerleşik Işleçler, öncelik ve Ilişkilendirilebilirlik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Koşullu Ifade Işleci](../c-language/conditional-expression-operator.md)