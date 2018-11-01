---
title: ML Önemli Hatası A1010
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: eb4d77b856e93a8d64ee6c51bec63ceae59b22e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449133"
---
# <a name="ml-fatal-error-a1010"></a>ML Önemli Hatası A1010

**eşleşmeyen blok iç içe geçme:**

Bir blok başına eşleşen bir bitiş yoktu veya blok son eşleşen başlayan bir sahip değildi. Aşağıdakilerden birini dahil:

- Gibi üst düzey bir yönerge [. Eğer](../../assembler/masm/dot-if.md), [. Yineleme](../../assembler/masm/dot-repeat.md), veya [. SIRADA](../../assembler/masm/dot-while.md).

- Bir koşullu derleme yönergesi gibi [IF](../../assembler/masm/if-masm.md), [YİNELEYİN](../../assembler/masm/repeat.md), veya **sırada**.

- Yapı veya birleşim tanımı.

- Bir yordamı tanımı.

- Segment tanımı.

- A [POPCONTEXT](../../assembler/masm/popcontext.md) yönergesi.

- Koşullu derleme yönergesi olduğu gibi bir [ELSE](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md), veya **ENDIF** eşleşen olmadan [IF](../../assembler/masm/if-masm.md).

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>