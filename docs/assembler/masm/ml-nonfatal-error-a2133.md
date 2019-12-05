---
title: ML Önemli Olmayan Hatası A2133
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2133
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
ms.openlocfilehash: c2d13aefe02543129340bcc307771a1026776d61
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854621"
---
# <a name="ml-nonfatal-error-a2133"></a>ML Önemli Olmayan Hatası A2133

**Invoke ile kayıt değerinin üzerine yazılır**

Bir kayıt bir yordama bağımsız değişken olarak geçirildi, ancak [Invoke](../../assembler/masm/invoke.md) tarafından oluşturulan kod diğer bağımsız değişkenleri geçirmek için kayıt içeriğini yok etti.

AX, AL, AH, EAX, DX, DL, DH ve EDX kayıtları, Assembler tarafından veri dönüştürme işlemi gerçekleştirmek için kullanılabilir.

Farklı bir kayıt kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>