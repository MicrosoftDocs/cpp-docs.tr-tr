---
title: İşaretçi aritmetiği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pointer arithmetic
- arithmetic pointer
ms.assetid: eb924a29-59d3-48a5-9d62-9424790730eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0cbaa5d71b0867ff355e194ad6c82c120148d76
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="pointer-arithmetic"></a>İşaretçi Aritmetiği
Bir işaretçi ve tamsayı içeren toplama işlemleri yalnızca bir dizi üye işaretçisi işleneni adresleri ve tamsayı değeri aynı dizinin sınırları içinde bir uzaklık üretir anlamlı sonuçlar verin. Tamsayı değeri bir adres uzaklık dönüştürüldüğünde Derleyici yalnızca bellek konumlarını aynı boyutta özgün adresi ve adres artı uzaklık arasında kalan varsayar.  
  
 Bu varsayım dizi üyeleri için geçerlidir. Tanımı gereği, bir dizi aynı türde değerler dizisidir; öğeleri bitişik bellek konumlarda bulunur. Ancak, depolama dizisi öğeleri dışındaki tüm türleri için aynı türde tanımlayıcıları doldurulması için kesin değildir. Diğer bir deyişle, boşlukları aynı türde bile konumlar bellek konumlar arasında yer alabilir. Bu nedenle, ekleme ya da tüm değerleri ancak dizi öğeleri adreslerinden çıkarılmasıyla sonuçlarını tanımlanmamış.  
  
 İki işaretçi değeri çıkarılır, benzer şekilde, yalnızca hiçbir boşlukları ile aynı türde değerler tarafından işlenen verilen adresleri arasında kalan dönüştürme varsayar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Ek İşleçleri](../c-language/c-additive-operators.md)