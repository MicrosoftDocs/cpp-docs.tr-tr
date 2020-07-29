---
title: Özel durum işleyicileri kısıtlamaları
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 1f80cb1574cbfef0783c7e55dcd198dfb822f566
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225910"
---
# <a name="restrictions-on-exception-handlers"></a>Özel durum işleyicileri kısıtlamaları

Kodda özel durum işleyicilerini kullanmanın asıl sınırlaması, bir **`goto`** **__try** deyim bloğuna geçmek için bir deyim kullanmmsıdır. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. Bir **__try** deyim bloğunun dışına atlayabilir ve özel durum işleyicilerini seçtiğiniz şekilde iç içe geçirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum Işleyicisi yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
