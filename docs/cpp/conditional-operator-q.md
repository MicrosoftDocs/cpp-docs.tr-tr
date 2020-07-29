---
title: 'Koşullu Işleç: &quest; :'
ms.date: 11/04/2016
f1_keywords:
- '?:'
- '?'
helpviewer_keywords:
- conditional operators [C++]
- '? : operator'
ms.assetid: 88643ee8-7100-4f86-880a-705ec22b6271
ms.openlocfilehash: 1f2c58d5b7c31e9c29a72aea0e62494549fc10a9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232332"
---
# <a name="conditional-operator-quest-"></a>Koşullu Işleç: &quest; :

## <a name="syntax"></a>Sözdizimi

```
expression ? expression : expression
```

## <a name="remarks"></a>Açıklamalar

Koşullu işleç (**?:**) üçlü bir işleçtir (üç işlenen alır). Koşullu işleç aşağıdaki gibi çalışır:

- İlk işlenen örtük olarak öğesine dönüştürülür **`bool`** . Değerlendirilir ve devam etmeden önce tüm yan etkileri tamamlanır.

- İlk işlenen **`true`** (1) olarak değerlendirilirse, ikinci işlenen değerlendirilir.

- İlk işlenen **`false`** (0) olarak değerlendirilirse, üçüncü işlenen değerlendirilir.

Koşullu işlecin sonucu, değerlendirilen işlenenin sonucudur — ikinci veya üçüncü. Son iki işlenenden yalnızca biri bir koşullu ifade içinde değerlendirilir.

Koşullu ifadeler sağdan sola birleşme özelliği içindedir. Birinci işlenen bir entegral veya işaretçi türü olmalıdır. Aşağıdaki kurallar ikinci ve üçüncü işlenenler için geçerlidir:

- Her iki işlenen de aynı türde ise, sonuç o tür olur.

- Her iki işlenen de aritmetik veya sabit listesi türlerindiyse, normal aritmetik dönüştürmeler ( [Standart dönüşümlerde](standard-conversions.md)ele alınmıştır), bunları ortak bir türe dönüştürmek için gerçekleştirilir.

- Her iki işlenen de işaretçi türlerisiyse veya biri işaretçi türü ise ve diğeri 0 olarak değerlendirilen bir sabit ifadeyse, bunları ortak bir türe dönüştürmek için işaretçi dönüşümleri gerçekleştirilir.

- Her iki işlenen de başvuru türlerindiyse, bunları ortak bir türe dönüştürmek için başvuru dönüştürmeleri yapılır.

- Her iki işlenen de void türünde ise, ortak tür void türüdür.

- Her iki işlenen de aynı kullanıcı tanımlı türde ise, ortak tür bu türdür.

- İşlenenler farklı türlere sahipse ve işlenenlerinden en az birinde Kullanıcı tanımlı tür varsa, ortak türü belirlemede dil kuralları kullanılır. (Aşağıdaki uyarıya bakın.)

Yukarıdaki listede bulunmayan ikinci ve üçüncü işlenenlerin birleşimleri geçersizdir. Hem ikinci hem de üçüncü işlenen aynı türdeyse ve her ikisi de l-değeri ise, sonucun türü ortak türdür ve bir l-değerdir.

> [!WARNING]
> İkinci ve üçüncü işlenenlerinin türleri özdeş değilse, C++ standardında belirtilen şekilde, karmaşık tür dönüştürme kuralları çağrılır. Bu dönüşümler, geçici nesnelerin oluşturulması ve yok edilmesi gibi beklenmeyen davranışlara neden olabilir. Bu nedenle, Kullanıcı tanımlı türleri koşullu işleçle (1) işlenen olarak kullanmaktan kaçının veya (2) Kullanıcı tanımlı türleri kullanıyorsanız, her işleneni açıkça ortak bir türe atamalısınız.

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

[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Koşullu Ifade Işleci](../c-language/conditional-expression-operator.md)
