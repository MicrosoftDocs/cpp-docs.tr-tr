---
title: Kayan nokta değerlerine tam sayılar atama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e00fdfc44c5939dbed2fb3258f0cab0023feeda0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381641"
---
# <a name="casting-integers-to-floating-point-values"></a>Kayan Nokta Değerlerine Tam Sayılar Atama
**ANSI 3.2.1.3** bir tamsayı özgün değeri tam olarak temsil edilemez kayan noktalı bir sayının dönüştürüldüğünde kesilmesi yönü  
  
 Bir tamsayı, tam olarak değeri temsil edemeyen bir kayan nokta değerine atandığında, değer en yakın uygun değere yuvarlanır (aşağı veya yukarı).  
  
 Örneğin, atama bir **uzun imzasız** (ile 32 bit duyarlık) için bir **float** (olan Mantis duyarlık 23 BITS içeriyor) 256 yakın çarpıma yuvarlar. **Uzun** değerleri için 4,294,966,913 4,294,967,167 tüm yuvarlanır için **float** 4,294,967,040 değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan Nokta Matematiği](../c-language/floating-point-math.md)