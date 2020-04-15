---
title: 'Koşullu Operatör: &quest; :'
ms.date: 11/04/2016
f1_keywords:
- '?:'
- '?'
helpviewer_keywords:
- conditional operators [C++]
- '? : operator'
ms.assetid: 88643ee8-7100-4f86-880a-705ec22b6271
ms.openlocfilehash: 4ba4c80d40450fd5975b047a1a4fca63146c5773
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337257"
---
# <a name="conditional-operator-quest-"></a>Koşullu Operatör: &quest; :

## <a name="syntax"></a>Sözdizimi

```
expression ? expression : expression
```

## <a name="remarks"></a>Açıklamalar

Koşullu işleç (**? :**) bir üçlü işleç (üç operands alır). Koşullu işleç aşağıdaki gibi çalışır:

- İlk operand örtülü **bool**dönüştürülür. Değerlendirilir ve devam etmeden önce tüm yan etkileri tamamlanır.

- Eğer ilk operand **doğru** (1) değerlendirirse, ikinci operand değerlendirilir.

- Eğer ilk operand **yanlış** (0) olarak değerlendirilirse, üçüncü operand değerlendirilir.

Koşullu işlecin sonucu, değerlendirilen işlenenin sonucudur — ikinci veya üçüncü. Son iki işlenenden yalnızca biri bir koşullu ifade içinde değerlendirilir.

Koşullu ifadeler sağdan sola birleşme özelliği içindedir. Birinci işlenen bir entegral veya işaretçi türü olmalıdır. Aşağıdaki kurallar ikinci ve üçüncü operands için geçerlidir:

- Her iki operands aynı türde ise, sonuç bu tür.

- Her iki operands aritmetik veya numaralandırma türleri ise, olağan aritmetik [dönüşümler (Standart Dönüşümler](standard-conversions.md)kapsamında) ortak bir türe dönüştürmek için gerçekleştirilir.

- Her iki operands işaretçi türleri veya bir işaretçi türü ve diğer 0'a değerlendirir sabit bir ifade ise, işaretçi dönüşümleri ortak bir türe dönüştürmek için gerçekleştirilir.

- Her iki operands başvuru türleri ise, başvuru dönüşümleri ortak bir türe dönüştürmek için gerçekleştirilir.

- Her iki operands türü geçersiz ise, ortak türü geçersiz türüdür.

- Her iki operands aynı kullanıcı tanımlı türünde ise, ortak türü bu türüdür.

- Operands farklı türleri varsa ve operands en az bir kullanıcı tanımlı türü varsa, o zaman dil kuralları ortak türünü belirlemek için kullanılır. (Aşağıdaki uyarıya bakın.)

Yukarıdaki listede bulunmayan ikinci ve üçüncü işlenenlerin birleşimleri geçersizdir. Hem ikinci hem de üçüncü işlenen aynı türdeyse ve her ikisi de l-değeri ise, sonucun türü ortak türdür ve bir l-değerdir.

> [!WARNING]
> İkinci ve üçüncü operands türleri aynı değilse, c++ Standardında belirtildiği gibi karmaşık tür dönüştürme kuralları çağrılır. Bu dönüşümler, geçici nesnelerin inşası ve imhası gibi beklenmeyen davranışlara yol açabilir. Bu nedenle, (1) koşullu işleç ile operands olarak kullanıcı tanımlı türleri kullanmaktan kaçınmanızı veya (2) kullanıcı tanımlı türleri kullanıyorsanız, her operand'ı açıkça ortak bir türe dökmenizi şiddetle tavsiye ederiz.

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
[Koşullu İfade İşleci](../c-language/conditional-expression-operator.md)
