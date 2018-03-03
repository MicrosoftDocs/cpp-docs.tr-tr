---
title: "Yön bayrağı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0a43bac113c013ecb93f5b6e84aa2075a052f8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="direction-flag"></a>Yön Bayrağı
Yön bayrağı Intel 80 x 86 işlemciler için belirli bir CPU bayrak ' dir. MOVS, MOVSD, MOVSW ve diğerleri gibi REP (Yineleme) önekini tüm derleme yönergeleri için geçerlidir. Yön bayrağı temizlenirse ilgili yönergeler için sağlanan adresleri artırılır.  
  
 C çalışma zamanı yordamları yön bayrağı temizlenir varsayalım. C çalışma zamanı işlevleri ile diğer işlevleri kullanıyorsanız, diğer işlevleri yön bayrağı bırakır veya orijinal durumuna geri emin olmalısınız. Giriş temizlenmesini yön bayrağı bekleniyor çalışma zamanı kodu daha hızlı ve daha verimli hale getirir.  
  
 Dize düzenlemesi ve ara bellek düzenlemesi yordamlarını gibi C çalışma zamanı kitaplığı işlevleri yön bayrağı açık olmasını bekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)