---
title: İçeri Aktarılanları bağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 551028999d11379c06d3319f01e882a33ad57936
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705204"
---
# <a name="binding-imports"></a>İçeri Aktarılanları Bağlama

Varsayılan bağlayıcı davranışı Gecikmeli yüklenen DLL için bağlanabilir içeri aktarma adres tablosu oluşturmaktır. DLL bağlıysa yardımcı işlevini çağırmak yerine ilişkili bilgileri kullanmak deneyecek **GetProcAddress** her başvurulan alır. Zaman damgası veya tercih edilen adresi bu yüklenen DLL'nin eşleşmiyorsa, yardımcı işlevini bağlı içeri aktarma adres tablosunun güncel değil ve yok edildiğinde devam edecek varsayar.

Hiçbir zaman DLL'nin Gecikmeli yüklenen içeri aktarmalar bağlamak istiyorsanız, belirtme [/delay](../../build/reference/delay-delay-load-import-settings.md): nobınd bağlayıcı'nın komut satırında, ilişkili içeri aktarma adres tablosunun resim dosyası içinde oluşturulan ve alıcı alanı yüklenmesini engeller.

## <a name="see-also"></a>Ayrıca Bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)