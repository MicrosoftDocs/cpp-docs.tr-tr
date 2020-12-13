---
description: 'Daha fazla bilgi edinin: ML önemli hatası A1010'
title: ML Önemli Hatası A1010
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: 4a00d9594c71c8a22942e869d109bf51176394c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129512"
---
# <a name="ml-fatal-error-a1010"></a>ML Önemli Hatası A1010

**eşleşmeyen blok iç içe:**

Bir blok başlangıcı eşleşen bir uca sahip değil veya bir blok ucunun eşleşen bir başlangıcı yok. Aşağıdakilerden biri olabilir:

- Gibi üst düzey bir yönerge [. Ise](dot-if.md), [. Veya TEKRARLAYıN](dot-repeat.md) [. WHILE](dot-while.md).

- [IF](if-masm.md), [Repeat](repeat.md)veya **WHILE** gibi koşullu derleme yönergesi.

- Bir yapı veya birleşim tanımı.

- Bir yordam tanımı.

- Bir segment tanımı.

- Bir [PopContext](popcontext.md) yönergesi.

- [Eşleşmeyen](if-masm.md)bir, [ElseIf](elseif-masm.md)veya **ENDIF** [gibi bir koşullu](else-masm.md)derleme yönergesi.

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](ml-error-messages.md)
