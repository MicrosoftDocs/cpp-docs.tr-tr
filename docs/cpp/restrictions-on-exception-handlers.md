---
title: Özel durum işleyicileriyle ilgili kısıtlamalar
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 54bf4a44d06eacd22dc4b9819d160d3c6a66c684
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179087"
---
# <a name="restrictions-on-exception-handlers"></a>Özel durum işleyicileriyle ilgili kısıtlamalar

Kodda özel durum işleyicilerini kullanmanın asıl sınırlaması, bir **__try** deyim bloğuna geçmek için **goto** ifadesini kullanmmın. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. Bir **__try** deyim bloğunun dışına atlayabilir ve özel durum işleyicilerini seçtiğiniz şekilde iç içe geçirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
