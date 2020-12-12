---
description: 'Daha fazla bilgi edinin: birleşimler depolaması'
title: Birleşimler Deposu
ms.date: 11/04/2016
helpviewer_keywords:
- storage, union
- union keyword [C], storage
- union keyword [C]
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
ms.openlocfilehash: bd95f1c1955049299192d0b4dbd333c86aecce25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205284"
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

`x`Birleşimin üyeleri, bildirimleri, bir değer işaretçisi, bir **`char`** **`char`** değer ve bir değerler dizisi olarak **`float`** . İçin ayrılan depolama alanı, `x` `f` `f` birleşimin en uzun üyesi olduğundan, 20 öğeli dizi için gereken depolama alanı. Birleşim ile ilişkili etiket olmadığından, türü adlandırılmamış veya "anonim" olur.

## <a name="see-also"></a>Ayrıca bkz.

[Birleşim bildirimleri](../c-language/union-declarations.md)
