---
title: Satır İçi Derlemeyi En İyi Duruma Getirme
ms.date: 08/30/2018
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
ms.openlocfilehash: d4956ba12e0bc268d78a895e6cb1ec6e2059262a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166886"
---
# <a name="optimizing-inline-assembly"></a>Satır İçi Derlemeyi En İyi Duruma Getirme

**Microsoft'a özgü**

Varlığı bir `__asm` bir işlev bloğunda iyileştirme çeşitli şekillerde etkiler. İlk olarak, derleyici en iyi duruma getirme dener `__asm` kendisini engelleyin. Derleme dilinde yazma, tam olarak ne devreye girer. İkincisi, varlığı bir `__asm` kaydetme değişken depolama blok etkiler. Derleyici, kayıt değişkenleri arasında önler bir `__asm` kaydın içeriğini tarafından değiştirilmesi bloke `__asm` blok. Son olarak, diğer bir işlevi genelinde iyileştirmeler eklenmesi, bir işlevde derleme dili tarafından etkilenir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>