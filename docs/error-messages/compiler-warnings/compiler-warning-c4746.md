---
title: Derleyici Uyarısı C4746
ms.date: 11/04/2016
f1_keywords:
- C4746
helpviewer_keywords:
- C4746
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
ms.openlocfilehash: 7179e2e6d4ec44355e7338ffc4e9ba36f5de47e4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165112"
---
# <a name="compiler-warning-c4746"></a>Derleyici Uyarısı C4746

'\<Expression > ' geçici erişimi/volatile: [ISO&#124;MS] ayarına tabidir; __iso_volatile_load/Store iç işlevlerini kullanmayı düşünün.

Geçici bir değişkene doğrudan erişildiğinde C4746 yayınlanır. Geliştiricilerin Şu anda belirtilen belirli geçici modelden etkilenen kod konumlarını belirlemesine yardımcı olmak için tasarlanmıştır ( [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneğiyle denetlenebilirler). Özellikle,/volatile: MS kullanıldığında derleyicinin ürettiği donanım belleği engellerinin yerini belirlemek yararlı olabilir.

Geçici bir modelden etkilenmeden geçici belleğe açıkça erişmek için __iso_volatile_load/Store iç bilgileri kullanılabilir. Bu iç bilgileri kullanmak, C4746 tetiklemez.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .
