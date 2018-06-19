---
title: Yön bayrağı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3737304d2443b4f67f00a03e23a0529ad5bcbfe3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387856"
---
# <a name="direction-flag"></a>Yön Bayrağı
Yön bayrağı Intel 80 x 86 işlemciler için belirli bir CPU bayrak ' dir. MOVS, MOVSD, MOVSW ve diğerleri gibi REP (Yineleme) önekini tüm derleme yönergeleri için geçerlidir. Yön bayrağı temizlenirse ilgili yönergeler için sağlanan adresleri artırılır.  
  
 C çalışma zamanı yordamları yön bayrağı temizlenir varsayalım. C çalışma zamanı işlevleri ile diğer işlevleri kullanıyorsanız, diğer işlevleri yön bayrağı bırakır veya orijinal durumuna geri emin olmalısınız. Giriş temizlenmesini yön bayrağı bekleniyor çalışma zamanı kodu daha hızlı ve daha verimli hale getirir.  
  
 Dize düzenlemesi ve ara bellek düzenlemesi yordamlarını gibi C çalışma zamanı kitaplığı işlevleri yön bayrağı açık olmasını bekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)