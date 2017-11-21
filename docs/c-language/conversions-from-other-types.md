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
ms.openlocfilehash: ed56c0c9ab3186200d3cbb47224dedc60adddb2f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="conversions-from-other-types"></a>Diğer Türlerden Dönüştürmeler
`enum` değeri tanımı gereği bir `int` değeri olduğu için `enum` değerine ilişkin dönüştürmeler, `int` türüne ilişkin dönüştürmelerle aynıdır. İçin Microsoft C derleyicisi bir tamsayı aynı olan bir **uzun**.  
  
 **Microsoft özel**  
  
 Yapı veya birleşim türleri arasında dönüştürme yapılmasına izin verilmez.  
  
 Herhangi bir değer `void` türüne dönüştürülebilir, ancak böyle bir dönüştürmenin sonucu yalnızca ifade deyiminde olduğu gibi ifade değerinin atıldığı bir bağlamda kullanılabilir.  
  
 `void` türünde, tanımı gereği hiçbir değer yoktur. Bu nedenle, başka bir türe dönüştürülemez ve diğer türler atama ile `void`'e dönüştürülemez. Ancak, açıkça yazmanız için bir değer çevirebilirsiniz `void`anlatıldığı gibi [tür atama dönüşümleri](../c-language/type-cast-conversions.md).  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama dönüşümleri](../c-language/assignment-conversions.md)