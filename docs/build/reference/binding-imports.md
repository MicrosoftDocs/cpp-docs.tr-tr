---
title: İçeri Aktarılanları Bağlama
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
ms.openlocfilehash: 6ee9d9cc180e77d817b7b52baa1a6eb5209a8365
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486352"
---
# <a name="binding-imports"></a>İçeri Aktarılanları Bağlama

Varsayılan bağlayıcı davranışı Gecikmeli yüklenen DLL için bağlanabilir içeri aktarma adres tablosu oluşturmaktır. DLL bağlıysa yardımcı işlevini çağırmak yerine ilişkili bilgileri kullanmak deneyecek **GetProcAddress** her başvurulan alır. Zaman damgası veya tercih edilen adresi bu yüklenen DLL'nin eşleşmiyorsa, yardımcı işlevini bağlı içeri aktarma adres tablosunun güncel değil ve yok edildiğinde devam edecek varsayar.

Hiçbir zaman DLL'nin Gecikmeli yüklenen içeri aktarmalar bağlamak istiyorsanız, belirtme [/delay](../../build/reference/delay-delay-load-import-settings.md): nobınd bağlayıcı'nın komut satırında, ilişkili içeri aktarma adres tablosunun resim dosyası içinde oluşturulan ve alıcı alanı yüklenmesini engeller.

## <a name="see-also"></a>Ayrıca Bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)