---
title: Birleşimler deposu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- storage, union
- union keyword [C], storage
- union keyword [C]
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 516de9411a91f4bb8dd5f8775544ef32e7863bb3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038275"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Birleşim Bildirimleri](../c-language/union-declarations.md)