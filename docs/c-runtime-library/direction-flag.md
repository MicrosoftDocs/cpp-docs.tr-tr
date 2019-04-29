---
title: Yön Bayrağı
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
ms.openlocfilehash: ead32fa7f09e9dd98130855ecd87ba3b3d454ef5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344427"
---
# <a name="direction-flag"></a>Yön Bayrağı

Yön bayrağı tüm Intel x86 uyumlu CPU'ları belirli bir CPU bayrağı ' dir. MOVS, MOVSD, MOVSW ve diğerleri gibi Temsilcisi (Yineleme) önek kullanan tüm derleme yönergeleri için geçerlidir. Yön bayrağı iptal edilirse ilgili yönergeler için sağlanan adreslerini artırıldı.

Yön bayrağı temizlenir C çalışma zamanı yordamları varsayılır. C çalışma zamanı işlevleri diğer işlevleri kullanıyorsanız, diğer işlevler yön bayrağı dokunmayın veya orijinal durumuna geri emin olmanız gerekir. Yön bayrağı giriş temizlenmesini bekleniyor çalışma zamanı kod daha hızlı ve daha verimli hale getirir.

Dize düzenlemesi ve ara bellek düzenlemesi yordamlar gibi C çalışma zamanı kitaplık işlevleri yön bayrağı açık olmasını bekler.

## <a name="see-also"></a>Ayrıca bkz.

[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
