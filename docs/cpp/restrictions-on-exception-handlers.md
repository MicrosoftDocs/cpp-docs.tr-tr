---
title: Özel durum işleyicileriyle ilgili kısıtlamalar
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 030d444443b3a6e3e2e0ac0e015619046a76d562
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245151"
---
# <a name="restrictions-on-exception-handlers"></a>Özel durum işleyicileriyle ilgili kısıtlamalar

Kodda özel durum işleyicilerini kullanmanın asıl sınırlaması, bir **__try** deyim bloğuna geçmek için **goto** ifadesini kullanmmın. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. Bir **__try** deyim bloğunun dışına atlayabilir ve özel durum işleyicilerini seçtiğiniz şekilde iç içe geçirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)