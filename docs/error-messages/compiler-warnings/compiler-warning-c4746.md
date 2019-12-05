---
title: Derleyici Uyarısı C4746
ms.date: 11/04/2016
f1_keywords:
- C4746
helpviewer_keywords:
- C4746
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
ms.openlocfilehash: 9e761deb1b8c1b00e025f49775a845d07985fd2c
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810575"
---
# <a name="compiler-warning-c4746"></a>Derleyici Uyarısı C4746

'\<Expression > ' geçici erişimi/volatile: [ISO&#124;MS] ayarına tabidir; __iso_volatile_load/Store iç işlevlerini kullanmayı düşünün.

Geçici bir değişkene doğrudan erişildiğinde C4746 yayınlanır. Geliştiricilerin Şu anda belirtilen belirli geçici modelden etkilenen kod konumlarını belirlemesine yardımcı olmak için tasarlanmıştır ( [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneğiyle denetlenebilirler). Özellikle,/volatile: MS kullanıldığında derleyicinin ürettiği donanım belleği engellerinin yerini belirlemek yararlı olabilir.

Geçici bir modelden etkilenmeden geçici belleğe açıkça erişmek için __iso_volatile_load/Store iç bilgileri kullanılabilir. Bu iç bilgileri kullanmak, C4746 tetiklemez.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .