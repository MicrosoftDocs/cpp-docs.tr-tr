---
title: İçeri Aktarılanları Bağlama
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
ms.openlocfilehash: 4058d738b87b69a73e8f18d977be8435a7d96a14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272929"
---
# <a name="binding-imports"></a>İçeri Aktarılanları Bağlama

Varsayılan bağlayıcı davranışı Gecikmeli yüklenen DLL için bağlanabilir içeri aktarma adres tablosu oluşturmaktır. DLL bağlıysa yardımcı işlevini çağırmak yerine ilişkili bilgileri kullanmak deneyecek **GetProcAddress** her başvurulan alır. Zaman damgası veya tercih edilen adresi bu yüklenen DLL'nin eşleşmiyorsa, yardımcı işlevini bağlı içeri aktarma adres tablosunun güncel değil ve yok edildiğinde devam edecek varsayar.

Hiçbir zaman DLL'nin Gecikmeli yüklenen içeri aktarmalar bağlamak istiyorsanız, belirtme [/delay](delay-delay-load-import-settings.md): nobınd bağlayıcı'nın komut satırında, ilişkili içeri aktarma adres tablosunun resim dosyası içinde oluşturulan ve alıcı alanı yüklenmesini engeller.

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](linker-support-for-delay-loaded-dlls.md)
