---
title: "Bir özel durum işleyicisi yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- structured exception handling [C++], exception handlers
- exception handling [C++], exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52d102f29a015ea077e9ec94a9f1ed63f44f7c1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="writing-an-exception-handler"></a>Özel Durum İşleyicisi Yazma
Özel durum işleyicileri genellikle belirli hatalar için yanıt vermede kullanılır. Ne yapılacağını bildiğiniz durumlar dışında, tüm özel durumları filtrelemek için exception-handling sözdizimini kullanabilirsiniz. Diğer özel durumlar, söz konusu özel durumları aramak yazılmış diğer işleyicilere (büyük olasılıkla çalışma zamanı kitaplığı veya işletim sistemindeki) aktarılmalıdır.  
  
 Özel durum işleyicileri try-except deyimini kullanır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Try-except deyimi](../cpp/try-except-statement.md)  
  
-   [Bir özel durum filtresi yazma](../cpp/writing-an-exception-filter.md)  
  
-   [Yazılım özel durumlarını oluşturma](../cpp/raising-software-exceptions.md)  
  
-   [Donanım özel durumları](../cpp/hardware-exceptions.md)  
  
-   [Özel durum işleyicileri kısıtlamaları](../cpp/restrictions-on-exception-handlers.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)