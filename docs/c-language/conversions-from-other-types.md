---
title: Diğer Türlerden Dönüştürmeler
ms.date: 01/29/2018
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
ms.openlocfilehash: bd00bbb8944a0273163fa0c5952be510c9dd697c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87200341"
---
# <a name="conversions-from-other-types"></a>Diğer türlerden dönüştürmeler

Bir değer **`enum`** tanım tarafından bir değer olduğundan **`int`** , bir değerden ve bu değerden Dönüştürmelere **`enum`** tür için olanlarla aynıdır **`int`** . Microsoft C derleyicisi için bir tamsayı, ile aynıdır **`long`** .

**Microsoft'a Özgü**

Yapı veya birleşim türleri arasında dönüştürme yapılmasına izin verilmez.

Herhangi bir değer türüne dönüştürülebilir **`void`** , ancak böyle bir dönüştürmenin sonucu yalnızca bir ifade değerinin atıldığı bağlamda (örneğin, ifade deyiminde) kullanılabilir.

**`void`** Türün tanımına göre değeri yok. Bu nedenle, başka bir türe dönüştürülemez ve diğer türler **`void`** atama ile öğesine dönüştürülemez. Ancak, **`void`** [tür atama dönüştürmelerinde](../c-language/type-cast-conversions.md)anlatıldığı gibi bir değeri açıkça türüne çevirebilirsiniz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Atama dönüştürmeleri](../c-language/assignment-conversions.md)
