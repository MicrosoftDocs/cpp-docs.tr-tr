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
ms.openlocfilehash: 7ac57a65d575ba6a9134f3c4474103735411847d
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75299110"
---
# <a name="one-dimensional-arrays"></a>Bir Boyutlu Diziler

Köşeli ayraçlar ( **[]** ) içindeki bir sonek ifadesi, bir dizi nesnesinin bir öğesinin alt simge olarak düzenlenmiş bir gösterimidir. Bir alt simge ifadesi, şöyle ifade edildiğinde *sonek ifadesinin* ötesinde *ifade* konumları olan adresteki değeri temsil eder

```
postfix-expression [ expression ]
```

Genellikle, *sonek ifadesi* tarafından temsil edilen değer, dizi tanımlayıcısı gibi bir işaretçi değeridir ve *ifade* ise tamsayı değeridir. Ancak, tüm sözdizimi, ifadelerden birinin işaretçi türü ve diğeri de İntegral türünde olması olabilir. Bu nedenle, tamsayı değeri *sonek ifadesi* konumunda olabilir ve işaretçi değeri, *ifadedeki*parantez veya "alt simge" konumunda olabilir. Örneğin, bu kod geçerlidir:

```c
// one_dimensional_arrays.c
int sum, *ptr, a[10];
int main() {
   ptr = a;
   sum = 4[ptr];
}
```

Alt simge ifadeleri genellikle dizi öğelerine başvurmak için kullanılır, ancak herhangi bir işaretçiye bir alt simge uygulayabilirsiniz. Değerlerin sırası ne olursa olsun, *ifade* köşeli ayraç ( **[]** ) içine alınmalıdır.

Alt simge ifadesi, tam sayı değeri işaretçi değerine eklenerek değerlendirilir ve ardından yöneltme işleci (<strong>\*</strong>) sonuca uygulanıyor. (Yöneltme işlecinin bir tartışması için bkz. [yöneltme ve adres işleçleri](../c-language/indirection-and-address-of-operators.md) .) Aslında, tek boyutlu bir dizi için aşağıdaki dört ifade eşdeğerdir, `a` bir işaretçi ve `b` bir tamsayı olduğunu varsayar:

```
a[b]
*(a + b)
*(b + a)
b[a]
```

Toplama işleci (eklenen [Işleçlere](../c-language/c-additive-operators.md)göre) için dönüştürme kurallarına göre, integral değeri, işaretçi tarafından ele alınan türün uzunluğuna göre çarpılarak bir adres denkleine dönüştürülür.

Örneğin, tanımlayıcı `line` bir `int` değerleri dizisine başvurduğunu varsayalım. Aşağıdaki yordam, `line[ i ]`alt simge ifadesini değerlendirmek için kullanılır:

1. `i` tamsayı değeri, bir `int` öğesinin uzunluğu olarak tanımlanan bayt sayısıyla çarpılır. `i` dönüştürülen değeri, `i` `int` konumlarını temsil eder.

1. Bu dönüştürülmüş değer, `line``int` konumlar `i` bir adres sağlamak için özgün işaretçi değerine (`line`) eklenir.

1. Yöneltme işleci yeni adrese uygulanır. Sonuç, bu konumdaki dizi öğesinin değeridir (ıntuicanlı, `line [ i ]`).

Alt simge ifadesi `line[0]`, `line` tarafından temsil edilen adresten gelen konum 0 olduğundan, satırın ilk öğesinin değerini temsil eder. Benzer şekilde, `line[5]` gibi bir ifade, satırdaki beş konum veya dizinin altıncı öğesi olan öğe sapmasını ifade eder.

## <a name="see-also"></a>Ayrıca bkz.

[Alt Simge İşleci:](../cpp/subscript-operator.md)
