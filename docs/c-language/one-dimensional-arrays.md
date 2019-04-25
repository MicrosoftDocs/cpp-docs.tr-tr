---
title: Bir Boyutlu Diziler
ms.date: 11/04/2016
helpviewer_keywords:
- brackets [ ]
- brackets [ ], arrays
- one-dimensional arrays
- arrays [C++], one-dimensional
- square brackets [ ]
- square brackets [ ], arrays
- subscript expressions
ms.assetid: e28536e5-3b77-46b5-97fd-9b938c771816
ms.openlocfilehash: bd3b495483a460f01fe1951ee4c8b5ac3b447701
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232352"
---
# <a name="one-dimensional-arrays"></a>Bir Boyutlu Diziler

Köşeli ayraçlar içinde bir ifade arkasından bir sonek ifadesi (**[]**) bir öğenin bir dizi nesnesinin simgeli gösterimidir. Alt simge ifadesi adresi değeri temsil eden *ifade* ötesinde konumlandırır *sonek ifadesi* olarak ifade edilen zaman

```
postfix-expression [ expression ]
```

Genellikle, tarafından temsil edilen değeri *sonek ifadesi* bir işaretçi değeri, bir dizi tanımlayıcısına gibi ve *ifade* bir integral değeridir. Ancak, tüm sözdizimsel olarak olan bir ifadenin bir işaretçi türünde olması ve diğeri Tamsayı türünde olması gereklidir. Tamsayı değeri bu nedenle olabilir *sonek ifadesi* konumu ve işaretçi değeri parantez içinde olabilir *ifade*, veya "alt simge," konum. Örneğin, bu yasal kodudur:

```
// one_dimensional_arrays.c
int sum, *ptr, a[10];
int main() {
   ptr = a;
   sum = 4[ptr];
}
```

Alt simge ifadeleri genellikle dizi öğelerine başvurmak için kullanılan, ancak herhangi bir işaretçiye bir alt simge uygulayabilirsiniz. Hangi değerleri sırasını *ifade* ayraçlar içine alınmalıdır (**[]**).

Alt simge ifadesi tam sayı değeri işaretçi değerine ekleyerek ve ardından yöneltme işlecini değerlendirilir (<strong>\*</strong>) sonucu. (Bkz [yöneltme ve adres işleçleri](../c-language/indirection-and-address-of-operators.md) yöneltme işlecinin bir tartışma.) Aslında, tek boyutlu bir dizi için aşağıdaki dört eşdeğer olduğunu varsayarak ifadelerdir `a` gösteren bir işaretçidir ve `b` bir tamsayıdır:

```
a[b]
*(a + b)
*(b + a)
b[a]
```

Toplama işleci dönüştürme kurallarına göre (içinde verilen [toplama işleçleri](../c-language/c-additive-operators.md)), tamsayı değeri, işaretçi tarafından ele alınan uzunluğunu çarpılmasıyla adresi uzaklık dönüştürülür.

Örneğin, tanımlayıcı varsayalım `line` dizilerine başvuruyor `int` değerleri. Alt simge ifadesi değerlendirmek için aşağıdaki yordamı kullanılan `line[ i ]`:

1. Tamsayı değeri `i` uzunluğu tanımlanan bayt sayısı çarpılır bir `int` öğesi. Dönüştürülmüş değeri `i` temsil `i` `int` konumları.

1. Dönüştürülen bu değer, orijinal işaretçi değerine eklenir (`line`) uzaklığını adresin elde etmek üzere `i` `int` gelen konumlandırır `line`.

1. Yöneltme işleci yeni adresine uygulanır. Bu konumda dizi öğesinin değeri sonucudur (sezgisel, `line [ i ]`).

Alt simge ifadesi `line[0]` satırının ilk öğenin değeri tarafından temsil edilen adrese uzaklığı beri temsil eden `line` 0'dır. Benzer şekilde, bir ifade gibi `line[5]` satır öğesi uzaklığı beş konumdan veya dizinin altıncı öğesinin anlamına gelir.

## <a name="see-also"></a>Ayrıca bkz.

[Alt Simge İşleci:](../cpp/subscript-operator.md)
