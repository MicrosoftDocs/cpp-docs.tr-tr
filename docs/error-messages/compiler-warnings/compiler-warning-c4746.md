---
title: Derleyici Uyarısı C4746 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d00c75b2b7cdf2fdafb4e109496a701fb561cb9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270904"
---
# <a name="compiler-warning-c4746"></a>Derleyici Uyarısı C4746
volatile erişimini '\<ifade >' / volatile tabi olan: [ISO&#124;ms] ayarlama; __iso_volatile_load/deposu iç işlevler kullanmayı düşünün.  
  
 Geçici bir değişken doğrudan erişildiğinde C4746 yayınlanır. Şu anda belirtilen belirli volatile model tarafından etkilenen kod konumlarını tanımlayan geliştiricilere yardımcı olmak için tasarlanmıştır (hangi denetlenebilir ile [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği). Özellikle, derleyicinin ürettiği donanım bellek engelleri bulma /volatile:ms kullanıldığında yararlı olabilir.  
  
 __İso_volatile_load/deposu iç bilgileri açıkça volatile modeli tarafından etkilenmeden geçici bellek erişmek için kullanılabilir. Bu yapı kullanarak C4746 tetiklemez.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.