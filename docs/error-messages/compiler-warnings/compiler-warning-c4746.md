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
ms.openlocfilehash: 1b88f51aa9365c0795c8d3d944ba9f3a8db059d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4746"></a>Derleyici Uyarısı C4746
volatile erişimini '\<ifade >' / volatile tabi olan: [ISO &#124; ms] ayarlama; __iso_volatile_load/deposu iç işlevler kullanmayı düşünün.  
  
 Geçici bir değişken doğrudan erişildiğinde C4746 yayınlanır. Şu anda belirtilen belirli volatile model tarafından etkilenen kod konumlarını tanımlayan geliştiricilere yardımcı olmak için tasarlanmıştır (hangi denetlenebilir ile [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği). Özellikle, derleyicinin ürettiği donanım bellek engelleri bulma /volatile:ms kullanıldığında yararlı olabilir.  
  
 __İso_volatile_load/deposu iç bilgileri açıkça volatile modeli tarafından etkilenmeden geçici bellek erişmek için kullanılabilir. Bu yapı kullanarak C4746 tetiklemez.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.