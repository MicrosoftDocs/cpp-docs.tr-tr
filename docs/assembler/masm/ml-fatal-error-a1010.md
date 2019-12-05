---
title: ML Önemli Hatası A1010
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: 6ec82f7f6d559d977a9aa039ed91689a0ef4d49a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856884"
---
# <a name="ml-fatal-error-a1010"></a>ML Önemli Hatası A1010

**eşleşmeyen blok iç içe:**

Bir blok başlangıcı eşleşen bir uca sahip değil veya bir blok ucunun eşleşen bir başlangıcı yok. Aşağıdakilerden biri olabilir:

- Gibi üst düzey bir yönerge [. Ise](../../assembler/masm/dot-if.md), [. Veya TEKRARLAYıN](../../assembler/masm/dot-repeat.md) [. WHILE](../../assembler/masm/dot-while.md).

- [IF](../../assembler/masm/if-masm.md), [Repeat](../../assembler/masm/repeat.md)veya **WHILE**gibi koşullu derleme yönergesi.

- Bir yapı veya birleşim tanımı.

- Bir yordam tanımı.

- Bir segment tanımı.

- Bir [PopContext](../../assembler/masm/popcontext.md) yönergesi.

- [Eşleşmeyen](../../assembler/masm/if-masm.md)bir, [ElseIf](../../assembler/masm/elseif-masm.md)veya **ENDIF** [gibi bir koşullu](../../assembler/masm/else-masm.md)derleme yönergesi.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>