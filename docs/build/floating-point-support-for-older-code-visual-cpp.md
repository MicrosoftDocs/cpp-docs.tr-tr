---
title: (Visual C++) eski kod için kayan nokta desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7285325bf1a934afcef337da318d019ec6fe375c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706816"
---
# <a name="floating-point-support-for-older-code-visual-c"></a>Eski Kod için Kayan Nokta Desteği (Visual C++)

Kayan nokta yığın kayıtları (MM0-MM7/ST0-ST7) ve MMX bağlam geçişleri boyunca korunur.  Bu kayıtlar için açık bir çağrı kuralı yok.  Bu yazmaçların kullanımı kesinlikle çekirdek modu kodu içinde kullanılamaz.

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)