---
title: "Sonlandırma işleyicisi yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- structured exception handling [C++], termination handlers
- exceptions [C++], terminating
- termination handlers [C++], writing
- handlers [C++]
- handlers [C++], termination
- termination handlers
- exception handling [C++], termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b9d4099a7f40acf0b5bfcc89f1c95cb880683b86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="writing-a-termination-handler"></a>Sonlandırma İşleyicisi Yazma
Bir özel durum işleyicisinin tersine, bir sonlandırma işleyicisi korunan kod bloğunun normal bir şekilde sonlandırılıp sonlandırılmadığına bakılmaksızın her zaman yürütülür. Sonlandırma işleyicisinin temel amacı bellek, tanıtıcılar ve dosyalar gibi kaynakları bir kod bölümünün yürütülmesinin nasıl sona erdiğine bakılmaksızın uygun bir şekilde kapatmaktır.  
  
 Sonlandırma işleyicileri, try-finally deyimini kullanır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Try-finally deyimi](../cpp/try-finally-statement.md)  
  
-   [Kaynakları temizleme](../cpp/cleaning-up-resources.md)  
  
-   [Özel durum işleme Eylemler zamanlama](../cpp/timing-of-exception-handling-a-summary.md)  
  
-   [Sonlandırma işleyicileri kısıtlamaları](../cpp/restrictions-on-termination-handlers.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)