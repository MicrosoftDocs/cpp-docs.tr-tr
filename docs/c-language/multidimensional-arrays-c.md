---
title: Çok Boyutlu Diziler (C)
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C], multidimensional
- multidimensional arrays
- subscript expressions
ms.assetid: 4ba5c360-1f17-4575-b370-45f62e1f2bc2
ms.openlocfilehash: f94cdff03763f689edbdedffad4ac56abec5ee53
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218838"
---
# <a name="multidimensional-arrays-c"></a>Çok Boyutlu Diziler (C)

Bir alt simge ifadesinde de aşağıdaki gibi birden fazla alt simge olabilir:

```
expression1 [ expression2 ] [ expression3 ] ...
```

Alt simge ifadeleri soldan sağa ilişkilendirilir. En soldaki indis ifadesi, *İfade1* **[** *İfade2* **]**, önce değerlendirilir. *İfade1* ve *Deyim2* ekleme işleminden elde edilen adres bir işaretçi ifadesi; ardından, yeni bir işaretçi ifadesi oluşturmak için bu işaretçi ifadesine *expression3* eklenir ve son alt simge ifadesi eklenene kadar bu şekilde devam eder. Son <strong>\*</strong> simge değeri bir dizi türüne (aşağıdaki örneklere bakın) bağlanmamışsa, yöneltme işleci () son alt indislenmiş ifadeden sonra uygulanır.

Birden çok alt simgeye sahip ifadeler, "çok boyutlu dizilerin" öğelerine başvurur. Çok boyutlu bir dizi, öğeleri dizi olan bir dizidir. Örneğin, üç boyutlu bir dizinin ilk öğesi iki boyutlu bir dizidir.

## <a name="examples"></a>Örnekler

Aşağıdaki örneklerde adlı bir dizi, `prop` her biri 4 x-6 değer dizisi olan üç öğe ile bildirilmiştir **`int`** .

```
int prop[3][4][6];
int i, *ip, (*ipp)[6];
```

`prop` dizisine yapılan başvuru aşağıdaki gibi görünür:

```
i = prop[0][0][1];
```

Yukarıdaki örnekte, öğesinin ikinci ayrı öğesine nasıl başvurabileceğiniz gösterilmektedir **`int`** `prop` . Diziler satıra göre depolanır, bu nedenle en hızlı son alt simge değişir; `prop[0][0][2]` ifadesi dizinin sonraki (üçüncü) öğesine başvurur ve bu düzen böyle devam eder.

```
i = prop[2][1][3];
```

Bu deyim, `prop`'un öğesine yapılan daha karmaşık bir başvurudur. İfade, aşağıdaki gibi değerlendirilir:

1. İlk alt simge, `2` 4-6 dizisinin boyutuyla çarpılır **`int`** ve işaretçi değerine eklenir `prop` . Sonuç, üçüncü 4 ile 6 `prop`'a işaret eder.

1. İkinci alt simge, `1` 6 öğeli dizinin boyutuyla çarpılır **`int`** ve tarafından temsil edilen adrese eklenir `prop[2]` .

1. 6 öğeli dizinin her öğesi bir **`int`** değerdir, bu nedenle son alt simge, `3` **`int`** öğesine eklenmeden önce boyutuyla çarpılır `prop[2][1]` . Elde edilen işaretçi, 6 öğeli dizinin dördüncü öğesine yöneliktir.

1. Yöneltme yol işleci işaretçi değerine uygulanır. Sonuç, **`int`** Bu adresteki öğedir.

Bu sonraki iki örnek, yöneltme işlecinin uygulanmadığı durumları gösterir.

```
ip = prop[2][1];

ipp = prop[2];
```

Bu deyimlerin ilkinde, `prop[2][1]` ifadesi üç boyutlu `prop` dizisinin geçerli bir başvurusudur; 6 öğeli bir diziye (yukarıda bildirilmiştir) başvurur. İşaretçi değeri bir diziye yönelik olduğu için yöneltme işleci uygulanmaz.

Benzer şekilde, ikinci `prop[2]` deyimindeki `ipp = prop[2];` ifadesinin sonucu, iki boyutlu diziye yönelik olan bir işaretçi değeridir.

## <a name="see-also"></a>Ayrıca bkz.

[Alt simge Işleci:](../cpp/subscript-operator.md)
