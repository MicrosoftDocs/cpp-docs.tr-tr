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
ms.openlocfilehash: 7519fb18ac7f24e79a5f7f664cb35f8eb5b3fd77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368934"
---
# <a name="binding-imports"></a>İçeri Aktarılanları Bağlama
Varsayılan bağlayıcı Gecikmeli yüklenen DLL için bağlanabilirse içeri aktarma adres tablosunu oluşturmak için davranıştır. DLL bağlıysa yardımcı işlevini ilişkili bilgi arama yerine kullanmayı dener **GetProcAddress** her başvurulan alır. Zaman damgası veya tercih edilen adres olanlar yüklenen DLL'nin eşleşmiyorsa, yardımcı işlevini ilişkili içeri aktarma adres tablosunu güncel değil ve onu mevcut değilse gibi devam edecek varsayar.  
  
 Hiçbir zaman DLL'nin Gecikmeli yüklenen içeri aktarmalar bağlamak istiyorsanız, belirtme [/delay](../../build/reference/delay-delay-load-import-settings.md): nobınd bağlayıcı'nın komut satırında, ilişkili içeri aktarma adres tablosunu oluşturulan ve alan alanı görüntü dosyasındaki yüklenmesini engeller.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)