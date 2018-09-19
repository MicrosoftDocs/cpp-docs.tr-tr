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
ms.openlocfilehash: 7db91b20b76ef06130cbb8357344352b820ed731
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093214"
---
# <a name="direction-flag"></a>Yön Bayrağı

Yön bayrağı Intel 80 x 86 işlemciler için belirli bir CPU bayrağı ' dir. MOVS, MOVSD, MOVSW ve diğerleri gibi Temsilcisi (Yineleme) önek kullanan tüm derleme yönergeleri için geçerlidir. Yön bayrağı iptal edilirse ilgili yönergeler için sağlanan adreslerini artırıldı.

Yön bayrağı temizlenir C çalışma zamanı yordamları varsayılır. C çalışma zamanı işlevleri diğer işlevleri kullanıyorsanız, diğer işlevler yön bayrağı dokunmayın veya orijinal durumuna geri emin olmanız gerekir. Yön bayrağı giriş temizlenmesini bekleniyor çalışma zamanı kod daha hızlı ve daha verimli hale getirir.

Dize düzenlemesi ve ara bellek düzenlemesi yordamlar gibi C çalışma zamanı kitaplık işlevleri yön bayrağı açık olmasını bekler.

## <a name="see-also"></a>Ayrıca Bkz.

[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)