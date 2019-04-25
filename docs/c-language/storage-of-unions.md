---
title: Birleşimler Deposu
ms.date: 11/04/2016
helpviewer_keywords:
- storage, union
- union keyword [C], storage
- union keyword [C]
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
ms.openlocfilehash: 49b99dc17fd7bdddd8a47e3bfd5913a70a7631a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157935"
---
# <a name="storage-of-unions"></a>Birleşimler Deposu

Birleşim değişkenini ile ilişkili depolama, en büyük birleşim üyesi için gerekli olan depolamadır. Daha küçük bir üye depolandığında, birleşim değişkenini kullanılmayan bellek alanı içerebilir. Tüm üyeleri aynı bellek alanı depolanır ve aynı adresinde başlatın. Depolanan değeri farklı bir üye için bir değer atanır her seferinde üzerine yazılır. Örneğin:

```
union         /* Defines a union named x */
{
    char *a, b;
    float f[20];
} x;
```

Üyeleri `x` işaretçisi, bildirim sırasına göre birleşim olan bir `char` değeri bir `char` değer ve bir dizi **float** değerleri. Depolama için ayrılan `x` 20 öğe dizisi için gerekli depolama `f`, bu yana `f` birleşim en uzun bir üyesidir. Hiçbir etiket birleşimi ile ilişkili olduğundan, adlandırılmamış ya da "anonim" türü

## <a name="see-also"></a>Ayrıca bkz.

[Birleşim Bildirimleri](../c-language/union-declarations.md)
