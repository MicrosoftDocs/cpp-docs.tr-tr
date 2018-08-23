---
title: -SUBSYSTEM | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /subsystem
dev_langs:
- C++
helpviewer_keywords:
- /SUBSYSTEM editbin option
- -SUBSYSTEM editbin option
- SUBSYSTEM editbin option
ms.assetid: 515e4cdf-3cc4-4659-8764-1f2757b49215
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75e0086f96f39814bd1a7e77df2adccc47d698fc
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42466016"
---
# <a name="subsystem"></a>/SUBSYSTEM
Yürütülebilir görüntü için gereken yürütme ortamını belirtir.  
  
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
        EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|  
        NATIVE|POSIX|WINDOWS|WINDOWSCE}[,major[.minor]]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek, işletim sistemi yürütme için çağrılacak alt sistemini belirtmek için görüntü düzenler.  
  
 Aşağıdaki alt sistemlerden istediğinizi belirleyebilirsiniz:  
  
 BOOT_APPLICATION  
 Windows önyükleme ortamında çalışan bir uygulama. Önyükleme uygulamaları hakkında daha fazla bilgi için bkz. [BCD WMI sağlayıcısı hakkında](/previous-versions/windows/desktop/bcd/about-bcd).  
  
 KONSOLU  
 Windows karakter modu uygulaması. İşletim sistemi konsol uygulamaları için bir konsol sağlar.  
  
 Genişletilebilir Bellenim Arabirimi (EFI) görüntüsü  
 EFI alt seçenekleri, Genişletilebilir Bellenim Arabirimi ortamında çalışan yürütülebilir resimleri açıklar. Bu ortam genellikle donanımla birlikte sağlanır ve işletim sistemi yüklenmeden önce yürütülür. EFI resim türleri arasındaki başlıca farklar şunlardır: görüntünün yüklendiği bellek konumu ve resim çağrısı döndüğünde alınmış eylemi. Denetimi geri döndüğünde, efı_applıcatıon görüntüsü kaldırılır. Efı_boot_servıce_drıver veya efı_runtıme_drıver yalnızca denetim bir hata koduyla döndüğünde kaldırılır. Efı_rom görüntüsü ROM'dan yürütülür. Daha fazla bilgi için bakın [birleşik EFI Forumu](http://www.uefi.org/) Web sitesi.  
  
 YEREL  
 Bir alt sistem ortamı olmadan çalışan kod — Örneğin, kernel modlu cihaz sürücüleri ve yerel sistem işlemleri. Bu seçenek genelde Windows Sistem özellikleri için ayrılmıştır.  
  
 POSIX  
 Windows, POSIX alt sisteminde çalışan bir uygulama.  
  
 WINDOWS  
 Windows grafik ortamında çalışan bir uygulama. Bu, hem Masaüstü uygulamaları hem de Evrensel Windows Platformu (UWP) uygulamaları içerir.  
  
 WINDOWSCE  
 WINDOWSCE alt sistemi, uygulamanın Windows CE çekirdeği sürümüne sahip bir cihazda çalıştırılacak amaçlandığını gösterir. Çekirdek sürümleri PocketPC, Windows Mobile, Windows Phone 7, Windows CE V1.0-6.0R3 ve Windows Embedded Compact 7 içerir.  
  
 İsteğe bağlı `major` ve `minor` değerleri belirtilen alt sistemin gerekli en düşük sürümü belirtin:  
  
-   Sürüm numarasının tam sayı bölümü — bölümü Ondalık ayırıcının solundaki — tarafından temsil edilen `major`.  
  
-   Sürüm numarasının kesirli bölümü — bölümü ondalık noktanın sağındaki — tarafından temsil edilen `minor`.  
  
-   Değerlerini `major` ve `minor` 0 ile 65.535 arasında olmalıdır.  
  
 Başlangıç adresi program için varsayılan alt sistem seçimi etkiler. Daha fazla bilgi için [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md), bağlayıcı/Entry:*işlevi* seçeneği.  
  
 Her alt sistemin büyük ve küçük sürüm numaraları için minimum ve varsayılan değerler dahil olmak üzere daha fazla bilgi için bkz. [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) bağlayıcı seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN Seçenekleri](../../build/reference/editbin-options.md)