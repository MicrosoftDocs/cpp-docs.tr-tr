---
title: -SUBSYSTEM | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /subsystem
dev_langs: C++
helpviewer_keywords:
- /SUBSYSTEM editbin option
- -SUBSYSTEM editbin option
- SUBSYSTEM editbin option
ms.assetid: 515e4cdf-3cc4-4659-8764-1f2757b49215
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 906ab5406fb6ccfb8905c3cf76ae6968ef0979da
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="subsystem"></a>/SUBSYSTEM
Yürütülebilir görüntü tarafından gerekli yürütme ortamı belirtir.  
  
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
        EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|  
        NATIVE|POSIX|WINDOWS|WINDOWSCE}[,major[.minor]]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek, işletim sistemi için yürütme çağırmanız gerekir hangi alt sistemi belirtmek için görüntü düzenler.  
  
 Aşağıdaki alt sistemleri birini belirtebilirsiniz:  
  
 BOOT_APPLICATION  
 Windows Önyükleme Ortamı'çalışan bir uygulama. Önyükleme uygulamalar hakkında daha fazla bilgi için bkz:[BCD WMI sağlayıcısını hakkında](http://msdn.microsoft.com/library/aa362639.aspx).  
  
 KONSOL  
 Bir Windows karakter modu uygulaması. İşletim sistemi konsol uygulamaları için bir konsol sağlar.  
  
 Genişletilebilir Bellenim Arabirimi (EFI) görüntüsü  
 EFI alt sistemi seçenekleri ve Genişletilebilir Bellenim Arabirimi ortamında çalışan yürütülebilir görüntüler açıklanmaktadır. Bu ortam genellikle donanım ile sağlanan ve işletim sistemi yüklenmeden önce yürütür. EFI resim türleri arasındaki temel farklar görüntü yüklenen bellek konumuna ve görüntünün çağrısı döndürüldüğünde alınmış eylemi ' dir. Denetim döndürdüğünde EFI_APPLICATION görüntüyü kaldırılır. Yalnızca denetim hata koduyla döndürürse EFI_BOOT_SERVICE_DRIVER veya EFI_RUNTIME_DRIVER kaldırılır. EFI_ROM görüntüyü ROM'dan yürütülür Üzerinde belirtimleri daha fazla bilgi için bkz [birleşik EFI Forumu](http://www.uefi.org/) Web sitesi.  
  
 YEREL  
 Bir alt sistemi ortamı çalışan kod — Örneğin, çekirdek modu aygıt sürücüleri ve yerel sistem işlemleri. Bu seçenek, genellikle Windows Sistem özellikleri için ayrılmıştır.  
  
 POSIX  
 Windows POSIX alt sisteminde çalışan bir uygulama.  
  
 WINDOWS  
 Windows grafiksel ortamda çalışan bir uygulama. Bu, hem Masaüstü uygulamaları hem de Windows mağazası uygulamaları içerir.  
  
 WINDOWSCE  
 Uygulamayı Windows CE çekirdek sürümü bir cihazda çalıştırma amaçlanmıştır WINDOWSCE alt sistemi gösterir. Çekirdek sürümleri PocketPC, Windows Mobile, Windows Phone 7, Windows CE V1.0-6.0R3 ve Windows Embedded Compact 7 içerir.  
  
 İsteğe bağlı `major` ve `minor` değerleri belirtilen alt sistemi gerekli en düşük sürümü belirtin:  
  
-   Sürüm numarasını tamsayı kısmını — Ondalık ayırıcının sol tarafındaki bölümüne — tarafından temsil edilen `major`.  
  
-   Sürüm numarasını kesirli kısmını — ondalık konumun sağında bölümü — tarafından temsil edilen `minor`.  
  
-   Değerlerini `major` ve `minor` 0 ile 65.535 arasında olmalıdır.  
  
 Alt sistemi seçimi başlangıç adresi program için varsayılan etkiler. Daha fazla bilgi için bkz: [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md), / Entry bağlayıcı:*işlevi* seçeneği.  
  
 Her alt birincil ve ikincil sürüm numaraları için minimum ve varsayılan değerler dahil olmak üzere daha fazla bilgi için bkz: [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) bağlayıcı seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN seçenekleri](../../build/reference/editbin-options.md)