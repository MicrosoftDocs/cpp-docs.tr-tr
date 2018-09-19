---
title: Diğer türlerden dönüştürmeler | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b443526248eb09accce8b35133235c71c06c2627
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094591"
---
# <a name="conversions-from-other-types"></a>Diğer türlerden dönüştürmeler

Bu yana bir **enum** değeri bir **int** tanımı gereği, dönüştürme ve ondan değeri bir **enum** değere eşit olanlar için aynı olan **int** türü. Microsoft C derleyicisi için bir tamsayı ile aynı olan bir **uzun**.

**Microsoft'a özgü**

Yapı veya birleşim türleri arasında dönüştürme yapılmasına izin verilmez.

Herhangi bir değer türüne dönüştürülebilir **void**, ancak böyle bir dönüştürme sonucu olarak atılan, bir ifade deyimi olduğu gibi bir ifade değeri olduğu bir bağlamda kullanılabilir.

**Void** türü tanımı tarafından herhangi bir değer vardır. Bu nedenle, başka bir türe dönüştürülemez ve diğer türleri dönüştürülemez **void** atama. Ancak, açıkça bir değer türüne çevirebilirsiniz **void**bölümünde açıklandığı gibi [tür atama dönüştürmeleri](../c-language/type-cast-conversions.md).

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Atama Dönüştürmeleri](../c-language/assignment-conversions.md)
