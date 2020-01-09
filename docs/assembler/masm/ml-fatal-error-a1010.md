---
title: ML Önemli Hatası A1010
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: b3141f8819a33281c70e34bd7772d4475886e557
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75312592"
---
# <a name="ml-fatal-error-a1010"></a>ML Önemli Hatası A1010

**eşleşmeyen blok iç içe:**

Bir blok başlangıcı eşleşen bir uca sahip değil veya bir blok ucunun eşleşen bir başlangıcı yok. Aşağıdakilerden biri olabilir:

- Gibi üst düzey bir yönerge [. Ise](dot-if.md), [. Veya TEKRARLAYıN](dot-repeat.md) [. WHILE](dot-while.md).

- [IF](if-masm.md), [Repeat](repeat.md)veya **WHILE**gibi koşullu derleme yönergesi.

- Bir yapı veya birleşim tanımı.

- Bir yordam tanımı.

- Bir segment tanımı.

- Bir [PopContext](popcontext.md) yönergesi.

- [Eşleşmeyen](if-masm.md)bir, [ElseIf](elseif-masm.md)veya **ENDIF** [gibi bir koşullu](else-masm.md)derleme yönergesi.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](ml-error-messages.md)
