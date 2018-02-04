---
title: "Diğer türlerden dönüştürmeler | Microsoft Docs"
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- values, converting
- type casts, conversion
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30021ad4058eed7d9fbca31b8e3d3141a55987f2
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="conversions-from-other-types"></a>Diğer türlerden dönüştürmeler

Bu yana bir **enum** değeri bir **int** tanımı gereği, dönüştürme ve ondan değeri bir **enum** değer için aynı olan **int** türü. İçin Microsoft C derleyicisi bir tamsayı aynı olan bir **uzun**.

**Microsoft Specific**

Yapı veya birleşim türleri arasında dönüştürme yapılmasına izin verilmez.

Herhangi bir değer türüne dönüştürülebilir **void**, ancak böyle bir dönüştürme sonucu atılan, örn. bir ifade deyimi bir ifade değeri olduğu yalnızca bağlamında kullanılabilir.

**Void** türü tanımı tarafından herhangi bir değer içeriyor. Bu nedenle, diğer bir türe dönüştürülemiyor ve diğer türleri dönüştürülemiyor **void** atamaya göre. Ancak, açıkça yazmanız için bir değer çevirebilirsiniz **void**anlatıldığı gibi [tür atama dönüşümleri](../c-language/type-cast-conversions.md).

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[Atama Dönüştürmeleri](../c-language/assignment-conversions.md)  
