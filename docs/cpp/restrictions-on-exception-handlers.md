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

The principal limitation to using exception handlers in code is that you cannot use a **goto** statement to jump into a **__try** statement block. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. You can jump out of a **__try** statement block and nest exception handlers as you choose.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)