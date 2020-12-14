---
description: 'Hakkında daha fazla bilgi edinin: One-Dimensional dizileri'
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
ms.openlocfilehash: 6c75d4b8d9a64f95f3698e6953949a71df60cad6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256906"
---
# <a name="one-dimensional-arrays"></a>Bir Boyutlu Diziler

Köşeli ayraçlar (**[]**) içindeki bir sonek ifadesi, bir dizi nesnesinin bir öğesinin alt simge olarak düzenlenmiş bir gösterimidir. Bir alt simge ifadesi, şöyle ifade edildiğinde *sonek ifadesinin* ötesinde *ifade* konumları olan adresteki değeri temsil eder

```
postfix-expression [ expression ]
```

Genellikle, *sonek ifadesi* tarafından temsil edilen değer, dizi tanımlayıcısı gibi bir işaretçi değeridir ve *ifade* ise tamsayı değeridir. Ancak, tüm sözdizimi, ifadelerden birinin işaretçi türü ve diğeri de İntegral türünde olması olabilir. Bu nedenle, tamsayı değeri *sonek ifadesi* konumunda olabilir ve işaretçi değeri, *ifadedeki* parantez veya "alt simge" konumunda olabilir. Örneğin, bu kod geçerlidir:

```c
// one_dimensional_arrays.c
int sum, *ptr, a[10];
int main() {
   ptr = a;
   sum = 4[ptr];
}
```

Alt simge ifadeleri genellikle dizi öğelerine başvurmak için kullanılır, ancak herhangi bir işaretçiye bir alt simge uygulayabilirsiniz. Değerlerin sırası ne olursa olsun, *ifade* köşeli ayraç (**[]**) içine alınmalıdır.

Alt simge ifadesi, tam sayı değeri işaretçi değerine eklenerek değerlendirilir ve ardından yöneltme işleci () uygulamaya eklenir <strong>\*</strong> . (Yöneltme işlecinin bir tartışması için bkz. [yöneltme ve adres işleçleri](../c-language/indirection-and-address-of-operators.md) .) Aslında, tek boyutlu bir dizi için aşağıdaki dört ifade eşdeğerdir, yani `a` bir işaretçi ve `b` bir tamsayıdır.

```
a[b]
*(a + b)
*(b + a)
b[a]
```

Toplama işleci (eklenen [Işleçlere](../c-language/c-additive-operators.md)göre) için dönüştürme kurallarına göre, integral değeri, işaretçi tarafından ele alınan türün uzunluğuna göre çarpılarak bir adres denkleine dönüştürülür.

Örneğin, tanımlayıcının `line` bir değerler dizisine başvurduğunu varsayın **`int`** . Aşağıdaki yordam, alt simge ifadesini değerlendirmek için kullanılır `line[ i ]` :

1. Tamsayı değeri, `i` bir öğenin uzunluğu olarak tanımlanan bayt sayısıyla çarpılır **`int`** . Dönüştürülmüş değeri `i` konumları temsil eder `i` **`int`** .

1. Bu dönüştürülen değer, konumundan konum konumu `line` olan bir adres sağlamak için özgün işaretçi değerine () eklenir `i` **`int`** `line` .

1. Yöneltme işleci yeni adrese uygulanır. Sonuç, bu konumdaki dizi öğesinin değeridir (ıntuicanlı, `line [ i ]` ).

Alt simge ifadesi `line[0]` , tarafından temsil edilen adresten alınan konum 0 olduğundan, satırın ilk öğesinin değerini temsil eder `line` . Benzer şekilde, gibi bir ifade, `line[5]` öğesi, satırdaki beş konum veya dizideki altıncı öğe olan öğe anlamına gelir.

## <a name="see-also"></a>Ayrıca bkz.

[Alt simge Işleci:](../cpp/subscript-operator.md)
