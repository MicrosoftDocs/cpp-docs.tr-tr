---
description: 'Daha fazla bilgi edinin: diğer türlerden dönüştürmeler'
title: Diğer Türlerden Dönüştürmeler
ms.date: 01/29/2018
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
ms.openlocfilehash: 0b9497c4873e42f9d08463c4ec1396b178b6f362
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293202"
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
