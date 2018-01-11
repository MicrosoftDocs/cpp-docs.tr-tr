---
title: "Diğer türlerden dönüştürmeler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8dbf2d3d269f5df3a028a5c416f8adca015be6dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="conversions-from-other-types"></a>Diğer Türlerden Dönüştürmeler
`enum` değeri tanımı gereği bir `int` değeri olduğu için `enum` değerine ilişkin dönüştürmeler, `int` türüne ilişkin dönüştürmelerle aynıdır. İçin Microsoft C derleyicisi bir tamsayı aynı olan bir **uzun**.  
  
 **Microsoft özel**  
  
 Yapı veya birleşim türleri arasında dönüştürme yapılmasına izin verilmez.  
  
 Herhangi bir değer `void` türüne dönüştürülebilir, ancak böyle bir dönüştürmenin sonucu yalnızca ifade deyiminde olduğu gibi ifade değerinin atıldığı bir bağlamda kullanılabilir.  
  
 `void` türünde, tanımı gereği hiçbir değer yoktur. Bu nedenle, başka bir türe dönüştürülemez ve diğer türler atama ile `void`'e dönüştürülemez. Ancak, açıkça yazmanız için bir değer çevirebilirsiniz `void`anlatıldığı gibi [tür atama dönüşümleri](../c-language/type-cast-conversions.md).  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama Dönüştürmeleri](../c-language/assignment-conversions.md)