---
title: Çok Boyutlu Diziler (C)
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C], multidimensional
- multidimensional arrays
- subscript expressions
ms.assetid: 4ba5c360-1f17-4575-b370-45f62e1f2bc2
ms.openlocfilehash: 34f5c60ba9ba5da869426ae4971808a5d75fee2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233369"
---
# <a name="multidimensional-arrays-c"></a>Çok Boyutlu Diziler (C)

Bir alt simge ifadesinde de aşağıdaki gibi birden fazla alt simge olabilir:

```
expression1 [ expression2 ] [ expression3 ] ...
```

Alt simge ifadeleri soldan sağa ilişkilendirilir. En soldaki alt simge ifadesi *İfade1* **[** *expression2* **]**, ilk olarak değerlendirilir. Eklemesini sonuçları adresi *İfade1* ve *expression2* bir işaretçi ifadesi; forms ardından *ifade3* yeni bir form için bu işaretçi ifadesine eklenir vb. son alt simge ifadesi eklenene dek işaretçi ifadesi. Yöneltme işleci (<strong>\*</strong>) (aşağıdaki örneklere bakın), son işaretçi değeri adresleri bir dizi türüne yönelik olmadığı sürece son simgeli ifade değerinden sonra uygulanır.

Birden çok alt simgeye sahip ifadeler, "çok boyutlu dizilerin" öğelerine başvurur. Çok boyutlu bir dizi, öğeleri dizi olan bir dizidir. Örneğin, üç boyutlu bir dizinin ilk öğesi iki boyutlu bir dizidir.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde `prop` adlı dizi, her biri `int` değerlerinin 4 ile 6 dizisi olan üç öğeyle bildirilir.

```
int prop[3][4][6];
int i, *ip, (*ipp)[6];
```

`prop` dizisine yapılan başvuru aşağıdaki gibi görünür:

```
i = prop[0][0][1];
```

Yukarıdaki örnekte, `int`'un ikinci `prop` öğesine nasıl başvurulacağı gösterilmektedir. Diziler satıra göre depolanır, bu nedenle en hızlı son alt simge değişir; `prop[0][0][2]` ifadesi dizinin sonraki (üçüncü) öğesine başvurur ve bu düzen böyle devam eder.

```
i = prop[2][1][3];
```

Bu deyim, `prop`'un öğesine yapılan daha karmaşık bir başvurudur. İfade, aşağıdaki gibi değerlendirilir:

1. İlk alt simge `2`, 4 ile 6 `int` dizisi ile çarpılır ve `prop` işaretçi değerine eklenir. Sonuç, üçüncü 4 ile 6 `prop`'a işaret eder.

1. İkinci alt simge `1`, 6 öğeli `int` dizisinin boyutuyla çarpılır ve `prop[2]` tarafından temsil edilen adrese eklenir.

1. 6 öğeli dizinin her öğesi bir `int` değeridir, bu nedenle son alt simge `3`, `int` öğesine eklenmeden önce `prop[2][1]` boyutu ile çarpılır. Elde edilen işaretçi, 6 öğeli dizinin dördüncü öğesine yöneliktir.

1. Yöneltme yol işleci işaretçi değerine uygulanır. Sonuç, bu adresteki `int` öğesidir.

Bu sonraki iki örnek, yöneltme işlecinin uygulanmadığı durumları gösterir.

```
ip = prop[2][1];

ipp = prop[2];
```

Bu deyimlerin ilkinde, `prop[2][1]` ifadesi üç boyutlu `prop` dizisinin geçerli bir başvurusudur; 6 öğeli bir diziye (yukarıda bildirilmiştir) başvurur. İşaretçi değeri bir diziye yönelik olduğu için yöneltme işleci uygulanmaz.

Benzer şekilde, ikinci `prop[2]` deyimindeki `ipp = prop[2];` ifadesinin sonucu, iki boyutlu diziye yönelik olan bir işaretçi değeridir.

## <a name="see-also"></a>Ayrıca bkz.

[Alt Simge İşleci:](../cpp/subscript-operator.md)
