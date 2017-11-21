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
ms.openlocfilehash: 42207a9bc1e9a355e6785a609ab0b130be063d55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="restrictions-on-exception-handlers"></a>Özel Durum İşleyicileri Kısıtlamaları
Kodda özel durum işleyicileri kullanmaya ilişkin birincil sınırlama, `goto` deyim bloğuna atlamak için `__try` deyimi kullanamamanızdır. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. `__try` deyim bloğundan dışarı atlayabilir ve seçtiğiniz özel durum işleyicilerini iç içe yerleştirebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)   
 [Yapılandırılmış özel durum işleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)