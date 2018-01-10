---
title: "İçeri Aktarılanları bağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f462eeea9f2bca566745d425b84bd1506f52fc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="binding-imports"></a>İçeri Aktarılanları Bağlama
Varsayılan bağlayıcı Gecikmeli yüklenen DLL için bağlanabilirse içeri aktarma adres tablosunu oluşturmak için davranıştır. DLL bağlıysa yardımcı işlevini ilişkili bilgi arama yerine kullanmayı dener **GetProcAddress** her başvurulan alır. Zaman damgası veya tercih edilen adres olanlar yüklenen DLL'nin eşleşmiyorsa, yardımcı işlevini ilişkili içeri aktarma adres tablosunu güncel değil ve onu mevcut değilse gibi devam edecek varsayar.  
  
 Hiçbir zaman DLL'nin Gecikmeli yüklenen içeri aktarmalar bağlamak istiyorsanız, belirtme [/delay](../../build/reference/delay-delay-load-import-settings.md): nobınd bağlayıcı'nın komut satırında, ilişkili içeri aktarma adres tablosunu oluşturulan ve alan alanı görüntü dosyasındaki yüklenmesini engeller.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)