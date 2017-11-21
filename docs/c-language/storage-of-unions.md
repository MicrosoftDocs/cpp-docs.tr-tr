---
title: "Birleşimler deposu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- storage, union
- union keyword [C], storage
- union keyword [C]
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cb349b2c1649b6e4e46fcc92829de87043d0c50a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="storage-of-unions"></a>Birleşimler Deposu
Birleşim değişkeni ile ilişkilendirilmiş depolama UNION en büyük üyesi için gerekli depolama alanına ' dir. Daha küçük bir üye depolandığında birleşim değişken kullanılmayan bellek alanı içerebilir. Tüm üyeleri aynı bellek alanı depolanır ve aynı adresinde başlatın. Depolanan değer değeri için farklı bir üye atanır her zaman üzerine yazılır. Örneğin:  
  
```  
union         /* Defines a union named x */  
{  
    char *a, b;  
    float f[20];  
} x;  
```  
  
 Üyeleri `x` gösteren bir işaretçi kendi bildirim sırasına birleşim olan bir `char` değeri, bir `char` değeri ve bir dizi **float** değerleri. Depolama birimi için ayrılan `x` 20 öğesi dizisi için gerekli depolama `f`, bu yana `f` uzun UNION üyesidir. Hiçbir etiketi birleşimi ile ilişkili olduğundan, adsız ya da "anonim" türü  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birleşim bildirimleri](../c-language/union-declarations.md)