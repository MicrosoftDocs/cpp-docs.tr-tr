---
description: 'Daha fazla bilgi: Gecikmeli yüklenen içeri aktarmalar dökümünü alma'
title: Gecikmeli yüklenen içeri aktarmalar dökümünü al
ms.date: 01/19/2021
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.openlocfilehash: 6a0fec0b10bc29ea919195302334a25f71de0abd
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666920"
---
# <a name="dump-delay-loaded-imports"></a>Gecikmeli yüklenen içeri aktarmalar dökümünü al

Gecikmeli yüklenen içeri aktarmalar kullanılarak dökülebilir [`dumpbin /imports`](imports-dumpbin.md) . Bu içeri aktarmalar, standart içeri aktarımlara göre biraz farklı bilgilerle gösterilir. Bunlar, listenin kendi bölümlerine bölünmüştür `/imports` ve açıkça Gecikmeli yüklenen içeri aktarmalar olarak etiketlendirilir. Görüntüde bir kaldırma bilgisi varsa, bu belirtilir. Bağlama bilgileri varsa, hedef DLL 'nin saat ve tarih damgası içeri aktarmaların bağlı adresleriyle birlikte belirtilir.

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
