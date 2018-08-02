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
ms.openlocfilehash: 8775f752a541d2a250e9c1c5a0c325b684335988
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464606"
---
# <a name="restrictions-on-exception-handlers"></a>Özel Durum İşleyicileri Kısıtlamaları
Kodda özel durum işleyicileri kullanmaya ilişkin birincil sınırlama, kullanamazsınız olduğu bir **goto** bloğuna atlamak için bir **__try** deyim bloğu. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. / Hızlı bir **__try** deyimi engelleme ve seçtiğiniz özel durum işleyicilerini iç içe yerleştirebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Bir özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)