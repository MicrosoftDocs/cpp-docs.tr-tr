---
title: ML önemli hatası A1010 | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1010
dev_langs:
- C++
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12b7e8698951e8ef59e0433134ec992af5d5f77f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676303"
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