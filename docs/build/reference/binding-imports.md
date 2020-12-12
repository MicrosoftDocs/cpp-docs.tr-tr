---
description: 'Daha fazla bilgi edinin: bağlama Içeri aktarmaları'
title: İçeri Aktarılanları Bağlama
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
ms.openlocfilehash: 7d1b4374bf1d3340a918f252d80102057febe053
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182716"
---
# <a name="binding-imports"></a>İçeri Aktarılanları Bağlama

Varsayılan bağlayıcı davranışı, Gecikmeli yüklenen DLL için bağlanabilir bir içeri aktarma adresi tablosu oluşturmaktır. DLL bağlı ise yardımcı işlevi, başvurulan içeri aktarmaların her birinde **GetProcAddress** çağırmak yerine bağlı bilgileri kullanmayı dener. Zaman damgası ya da tercih edilen adres yüklenen DLL 'nin olanlarla eşleşmiyorsa, yardımcı işlevi, bağlantılı içeri aktarma adresi tablosunun güncel olmadığını varsayar ve mevcut olmadığı gibi devam eder.

DLL 'nin Gecikmeli yüklenen içeri aktarmaları bağlamayı hiç yapmadıysanız, bağlayıcının komut satırında [/Delay](delay-delay-load-import-settings.md): nobind belirtildiğinde, bağlı içeri aktarma adresi tablosunun oluşturulmasını ve görüntü dosyasındaki alan kullanılmasını önleyecaksınız.

## <a name="see-also"></a>Ayrıca bkz.

[Delay-Loaded dll 'Ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
