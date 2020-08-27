---
title: Özel durum işleyicileri kısıtlamaları
description: Yapılandırılmış özel durum işleme bloklarına atlama kısıtlamalarını açıklar.
ms.date: 08/24/2020
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: c4182f065789533bf7599621d8d2829b2d52d6ed
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898452"
---
# <a name="restrictions-on-exception-handlers"></a>Özel durum işleyicileri kısıtlamaları

Kodda özel durum işleyicilerini kullanmanın asıl sınırlaması, deyim **`goto`** bloğuna geçmek için bir deyim kullanamıyoruz **`__try`** . Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. Bir deyim bloğunun dışına geçebilmeniz **`__try`** ve özel durum işleyicilerini seçtiğiniz şekilde iç içe geçirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
