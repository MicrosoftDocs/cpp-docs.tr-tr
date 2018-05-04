---
title: Özel durum işleyicileri kısıtlamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f739152b502a156dc62dfab279e5ad044cfff99
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="restrictions-on-exception-handlers"></a>Özel Durum İşleyicileri Kısıtlamaları
Kodda özel durum işleyicileri kullanmaya ilişkin birincil sınırlama, `goto` deyim bloğuna atlamak için `__try` deyimi kullanamamanızdır. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. `__try` deyim bloğundan dışarı atlayabilir ve seçtiğiniz özel durum işleyicilerini iç içe yerleştirebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)