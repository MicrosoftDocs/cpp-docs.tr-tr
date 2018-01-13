---
title: "Özel durum işleyicileri kısıtlamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9e55ba9c36fdbc5f3c19e7ad81373599ab138e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="restrictions-on-exception-handlers"></a>Özel Durum İşleyicileri Kısıtlamaları
Kodda özel durum işleyicileri kullanmaya ilişkin birincil sınırlama, `goto` deyim bloğuna atlamak için `__try` deyimi kullanamamanızdır. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. `__try` deyim bloğundan dışarı atlayabilir ve seçtiğiniz özel durum işleyicilerini iç içe yerleştirebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)