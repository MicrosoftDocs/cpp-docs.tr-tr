---
title: Özel Durum İşleyicileri Kısıtlamaları
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 7d5bf20da61f4b9f5012b7f2aab932dfc904c302
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573998"
---
# <a name="restrictions-on-exception-handlers"></a>Özel Durum İşleyicileri Kısıtlamaları

Kodda özel durum işleyicileri kullanmaya ilişkin birincil sınırlama, kullanamazsınız olduğu bir **goto** bloğuna atlamak için bir **__try** deyim bloğu. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. / Hızlı bir **__try** deyimi engelleme ve seçtiğiniz özel durum işleyicilerini iç içe yerleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)