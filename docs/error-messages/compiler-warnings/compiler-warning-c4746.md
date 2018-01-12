---
title: "Derleyici Uyarısı C4746 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f92bae0e75d9a09de874cd999c044e703b3f3171
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4746"></a>Derleyici Uyarısı C4746
volatile erişimini '\<ifade >' / volatile tabi olan: [ISO &#124; ms] ayarlama; __iso_volatile_load/deposu iç işlevler kullanmayı düşünün.  
  
 Geçici bir değişken doğrudan erişildiğinde C4746 yayınlanır. Şu anda belirtilen belirli volatile model tarafından etkilenen kod konumlarını tanımlayan geliştiricilere yardımcı olmak için tasarlanmıştır (hangi denetlenebilir ile [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği). Özellikle, derleyicinin ürettiği donanım bellek engelleri bulma /volatile:ms kullanıldığında yararlı olabilir.  
  
 __İso_volatile_load/deposu iç bilgileri açıkça volatile modeli tarafından etkilenmeden geçici bellek erişmek için kullanılabilir. Bu yapı kullanarak C4746 tetiklemez.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.