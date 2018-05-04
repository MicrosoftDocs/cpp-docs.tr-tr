---
title: Hatalı erişim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c322ff9e411cc6c9ef845fdd9a289a9ed5c49d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="improper-access-to-a-union"></a>Birleşime Düzgün Olmayan Erişim
**ANSI 3.3.2.3** birleşim nesne üyesi, farklı bir tür üyesi kullanılarak erişilir  
  
 İki tür birleşimi bildirilmiş ve bir değer depolanır, ancak birleşimi bir türü ile erişilen, sonuçları güvenilir değil.  
  
 Örneğin, bir birleşimi **float** ve `int` bildirilmedi. A **float** değeri depolanır, ancak programı daha sonra değeri olarak erişen bir `int`. Böyle bir durumda, iç depolaması ve değeri değişir **float** değerleri. Tamsayı değeri güvenilir olmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)