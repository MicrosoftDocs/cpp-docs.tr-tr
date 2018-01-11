---
title: "Hatalı erişim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71fe791e776450d21878144447cf95cdedb34875
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="improper-access-to-a-union"></a>Birleşime Düzgün Olmayan Erişim
**ANSI 3.3.2.3** birleşim nesne üyesi, farklı bir tür üyesi kullanılarak erişilir  
  
 İki tür birleşimi bildirilmiş ve bir değer depolanır, ancak birleşimi bir türü ile erişilen, sonuçları güvenilir değil.  
  
 Örneğin, bir birleşimi **float** ve `int` bildirilmedi. A **float** değeri depolanır, ancak programı daha sonra değeri olarak erişen bir `int`. Böyle bir durumda, iç depolaması ve değeri değişir **float** değerleri. Tamsayı değeri güvenilir olmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)