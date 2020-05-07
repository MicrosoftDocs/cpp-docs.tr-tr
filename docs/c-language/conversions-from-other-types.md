---
title: Diğer Türlerden Dönüştürmeler
ms.date: 01/29/2018
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
ms.openlocfilehash: f9f2d73e57c576dcf8afed008a74e5e7dd9b9d6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312472"
---
# <a name="conversions-from-other-types"></a>Diğer türlerden dönüştürmeler

Bir **sabit listesi** değeri tanımına göre **bir int** değeri olduğundan, **enum** değerine ve bu değerden gelen dönüştürmeler, **int** türüyle aynı olanlardır. Microsoft C derleyicisi için, bir tamsayı **Long**ile aynıdır.

**Microsoft'a Özgü**

Yapı veya birleşim türleri arasında dönüştürme yapılmasına izin verilmez.

Herhangi bir değer **void**türüne dönüştürülebilir, ancak böyle bir dönüştürmenin sonucu yalnızca bir ifade değerinin atıldığı bağlamda (örneğin, ifade deyiminde) kullanılabilir.

**Void** türü tanımına göre değer içermez. Bu nedenle, başka bir türe dönüştürülemez ve diğer türler atamaya göre **void** olarak dönüştürülemez. Ancak, [tür atama dönüştürmelerinde](../c-language/type-cast-conversions.md)anlatıldığı gibi, bir değeri açıkça **void**türüne çevirebilirsiniz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Atama Dönüştürmeleri](../c-language/assignment-conversions.md)
