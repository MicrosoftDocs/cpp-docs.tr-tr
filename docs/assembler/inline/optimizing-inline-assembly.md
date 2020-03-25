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
ms.openlocfilehash: 0051b16ddc19e233cfac2688c0b77e1e023f0833
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169272"
---
# <a name="optimizing-inline-assembly"></a>Satır İçi Derlemeyi En İyi Duruma Getirme

**Microsoft 'a özgü**

Bir işlevde `__asm` bloğunun varlığı, iyileştirmeyi birkaç şekilde etkiler. İlk olarak, derleyici `__asm` bloğunun kendisini iyileştirmenize çalışır. Derleme dilinde yazdığınız özellikler tam olarak sizin alacağınız şeydir. İkincisi, bir `__asm` bloğunun varlığı, YAZMAÇ değişkeni depolamayı etkiler. Derleyici, kayıt içerikleri `__asm` bloğu tarafından değiştirilebiliyorsa, `__asm` bir blok genelinde değişkenlerin kaydedilmesini önler. Son olarak, diğer işlev genelindeki bazı iyileştirmeler, derleme dilinin bir işleve dahil edilmesini etkiler.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
