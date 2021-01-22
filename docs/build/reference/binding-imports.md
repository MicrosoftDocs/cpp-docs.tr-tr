---
description: Gecikmeli yüklenen içeri aktarmaları bağlama hakkında daha fazla bilgi edinin
title: Gecikmeli yüklenen içeri aktarmaları bağlama
ms.date: 01/19/2021
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.openlocfilehash: 49d321a30eeb3ab12ec832fb86a662f2035e1e3a
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666946"
---
# <a name="bind-delay-loaded-imports"></a>Gecikmeli yüklenen içeri aktarmaları bağlama

Varsayılan bağlayıcı davranışı, Gecikmeli yüklenen DLL için bağlanabilir bir içeri aktarma adresi tablosu (ıAT) oluşturmaktır. DLL bağlı ise, yardımcı işlevi, `GetProcAddress` başvurulan her içeri aktarmaların her birine çağırmak yerine bağlı bilgileri kullanmayı dener. Zaman damgası ya da tercih edilen adres yüklenen DLL 'nin ile eşleşmezse, yardımcı işlevi, bağlantılı içeri aktarma adresi tablosunun güncel olmadığını varsayar. IAT yok gibi devam eder.

Bir DLL 'nin Gecikmeli yüklenen içeri aktarmalarını bağlamayı hiç belirtmediğiniz takdirde [`/delay:nobind`](delay-delay-load-import-settings.md) bağlayıcı komut satırında öğesini belirtin. Bağlayıcı, görüntü dosyasına alan kaydeden, bağlantılı içeri aktarma adresi tablosunu oluşturmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
