---
title: ML önemli hatası A1011 | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1011
dev_langs:
- C++
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32949773b869d189516a381ca7df941760a1e4e4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690814"
---
# <a name="ml-fatal-error-a1011"></a>ML Önemli Hatası A1011

**yönergesi, denetim bloğu içinde olmalıdır**

Derleyici burada değil beklenen üst düzey bir yönergesi bulundu. Aşağıdaki yönergeleri bulundu:

- [. BAŞKA](../../assembler/masm/dot-else.md) olmadan [. EĞER](../../assembler/masm/dot-if.md)

- [. ENDIF](../../assembler/masm/dot-endif.md) olmadan [. EĞER](../../assembler/masm/dot-if.md)

- [. ENDW](../../assembler/masm/dot-endw.md) olmadan [. WHILE](../../assembler/masm/dot-while.md)

- [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md) olmadan [. YİNELE](../../assembler/masm/dot-repeat.md)

- [. Devam](../../assembler/masm/dot-continue.md) olmadan [. SIRADA](../../assembler/masm/dot-while.md) veya [. YİNELE](../../assembler/masm/dot-repeat.md)

- [. BREAK](../../assembler/masm/dot-break.md) olmadan [. SIRADA](../../assembler/masm/dot-while.md) veya [. YİNELE](../../assembler/masm/dot-repeat.md)

- [. BAŞKA](../../assembler/masm/dot-else.md) aşağıdaki `.ELSE`

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>