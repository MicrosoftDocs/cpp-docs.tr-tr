---
title: Yön Bayrağı
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- direction flag
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
ms.openlocfilehash: e5177f206e46227fa693ef8d4bd1848b06374af7
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849912"
---
# <a name="direction-flag"></a>Yön Bayrağı

Yön bayrağı tüm Intel x86 uyumlu CPU'ları belirli bir CPU bayrağı ' dir. MOVS, MOVSD, MOVSW ve diğerleri gibi Temsilcisi (Yineleme) önek kullanan tüm derleme yönergeleri için geçerlidir. Yön bayrağı iptal edilirse ilgili yönergeler için sağlanan adreslerini artırıldı.

Yön bayrağı temizlenir C çalışma zamanı yordamları varsayılır. C çalışma zamanı işlevleri diğer işlevleri kullanıyorsanız, diğer işlevler yön bayrağı dokunmayın veya orijinal durumuna geri emin olmanız gerekir. Yön bayrağı giriş temizlenmesini bekleniyor çalışma zamanı kod daha hızlı ve daha verimli hale getirir.

Dize düzenlemesi ve ara bellek düzenlemesi yordamlar gibi C çalışma zamanı kitaplık işlevleri yön bayrağı açık olmasını bekler.

## <a name="see-also"></a>Ayrıca Bkz.

[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
