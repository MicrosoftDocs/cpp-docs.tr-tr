---
description: 'Daha fazla bilgi edinin: satır Içi derlemeyi Iyileştirme'
title: Satır İçi Derlemeyi En İyi Duruma Getirme
ms.date: 08/30/2018
helpviewer_keywords:
- storage, optimizing in inline assembly
- optimization, inline assembly
- inline assembly, optimizing
- optimizing performance, inline assembly
- __asm keyword [C++], optimizing
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
ms.openlocfilehash: 62c4dad85128089cdcf85f4156884747f928338f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122102"
---
# <a name="optimizing-inline-assembly"></a>Satır İçi Derlemeyi En İyi Duruma Getirme

**Microsoft'a Özgü**

**`__asm`** Bir işlev içindeki bir bloğun varlığı, iyileştirmeyi birkaç şekilde etkiler. İlk olarak, derleyici blok kendisini iyileştirmenize çalışır **`__asm`** . Derleme dilinde yazdığınız özellikler tam olarak sizin alacağınız şeydir. İkincisi, bir bloğun varlığı, **`__asm`** yazmaç değişkeni depolamayı etkiler. **`__asm`** Kayıt içeriği blok tarafından değiştirilebiliyorsa derleyici bir blok genelinde değişkenlerin kaydedilmesini önler **`__asm`** . Son olarak, diğer işlev genelindeki bazı iyileştirmeler, derleme dilinin bir işleve dahil edilmesini etkiler.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır içi assembler](../../assembler/inline/inline-assembler.md)<br/>
