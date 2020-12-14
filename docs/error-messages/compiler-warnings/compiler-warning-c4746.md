---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4746'
title: Derleyici Uyarısı C4746
ms.date: 11/04/2016
f1_keywords:
- C4746
helpviewer_keywords:
- C4746
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
ms.openlocfilehash: 09c6b6968e7180e19955d84fdb69c9113509c39c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315042"
---
# <a name="compiler-warning-c4746"></a>Derleyici Uyarısı C4746

geçici ' ' erişimi \<expression> /volatile: [ıso&#124;MS] ayarına tabidir; __İso_volatile_load/Store iç işlevlerini kullanmayı düşünün.

Geçici bir değişkene doğrudan erişildiğinde C4746 yayınlanır. Geliştiricilerin Şu anda belirtilen belirli geçici modelden etkilenen kod konumlarını belirlemesine yardımcı olmak için tasarlanmıştır ( [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneğiyle denetlenebilirler). Özellikle,/volatile: MS kullanıldığında derleyicinin ürettiği donanım belleği engellerinin yerini belirlemek yararlı olabilir.

Geçici bir modelden etkilenmeden geçici belleğe açıkça erişmek için __iso_volatile_load/Store iç bilgileri kullanılabilir. Bu iç bilgileri kullanmak, C4746 tetiklemez.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .
