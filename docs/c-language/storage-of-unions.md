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

Birleşim değişkeniyle ilişkili depolama alanı, birleşimin en büyük üyesi için gereken depolama alanı. Daha küçük bir üye depolandığında, UNION değişkeni kullanılmamış bellek alanı içerebilir. Tüm üyeler aynı bellek alanında depolanır ve aynı adresle başlatılır. Her bir değer farklı bir üyeye atandığında depolanan değerin üzerine yazılır. Örneğin:

```
union         /* Defines a union named x */
{
    char *a, b;
    float f[20];
} x;
```

`x` Birleşimin üyeleri, bildirimleri sırasıyla, bir `char` değer işaretçisi, bir `char` değer ve bir **float** değerleri dizisi olarak bulunur. İçin `x` ayrılan depolama alanı, birleşimin en uzun üyesi `f` `f` olduğundan, 20 öğeli dizi için gereken depolama alanı. Birleşim ile ilişkili etiket olmadığından, türü adlandırılmamış veya "anonim" olur.

## <a name="see-also"></a>Ayrıca bkz.

[Birleşim Bildirimleri](../c-language/union-declarations.md)
