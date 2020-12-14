---
description: Daha fazla bilgi edinin:/SUBSYSTEM
title: /SUBSYSTEM
ms.date: 11/04/2016
f1_keywords:
- /subsystem_editbin
helpviewer_keywords:
- /SUBSYSTEM editbin option
- -SUBSYSTEM editbin option
- SUBSYSTEM editbin option
ms.assetid: 515e4cdf-3cc4-4659-8764-1f2757b49215
ms.openlocfilehash: 24c334099eca93fc0f6e5790e78ed99049c572a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230243"
---
# <a name="subsystem"></a>/SUBSYSTEM

Yürütülebilir görüntü için gereken yürütme ortamını belirtir.

```
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
        EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|
        NATIVE|POSIX|WINDOWS|WINDOWSCE}[,major[.minor]]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek görüntüyü, işletim sisteminin yürütme için hangi alt sistemi çağırmak gerektiğini belirtecek şekilde düzenler.

Aşağıdaki alt sistemlerden herhangi birini belirtebilirsiniz:

**BOOT_APPLICATION**<br/>
Windows önyükleme ortamında çalışan bir uygulama. Önyükleme uygulamaları hakkında daha fazla bilgi için bkz. [BCD WMI sağlayıcısı hakkında](/previous-versions/windows/desktop/bcd/about-bcd).

**KONSOLA**<br/>
Bir Windows karakter modu uygulaması. İşletim sistemi konsol uygulamaları için bir konsol sağlar.

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
Genişletilebilir Bellenim Arabirimi (EFı) görüntüsü

EFı alt sistem seçenekleri, Genişletilebilir Bellenim Arabirimi ortamında çalışan yürütülebilir görüntüleri anlatmaktadır. Bu ortam genellikle donanımla birlikte sağlanır ve işletim sistemi yüklenmeden önce yürütülür. EFı görüntü türleri arasındaki önemli farklılıklar, görüntünün yüklendiği bellek konumudur ve görüntüye yapılan çağrı döndürüldüğünde gerçekleştirilecek eylemdir. Denetim döndüğünde EFI_APPLICATION bir görüntü kaldırılır. Bir EFI_BOOT_SERVICE_DRIVER veya EFI_RUNTIME_DRIVER yalnızca denetim bir hata koduyla döndürülürse kaldırılır. ROM 'dan bir EFI_ROM görüntüsü yürütülür. Daha fazla bilgi için bkz. [BIRLEŞIK EFI Forumu](https://www.uefi.org/) Web sitesindeki özellikler.

**Yerel**<br/>
Bir alt sistem ortamı olmadan çalışan kod (örneğin, çekirdek modu cihaz sürücüleri ve yerel sistem süreçler). Bu seçenek, genellikle Windows sistem özellikleri için ayrılmıştır.

**OF**<br/>
Windows 'daki POSIX alt sisteminde çalışan bir uygulama.

**PENCERELERIN**<br/>
Windows grafik ortamında çalışan bir uygulama. Bu, hem masaüstü uygulamaları hem de Evrensel Windows Platformu (UWP) uygulamalarını içerir.

**WıNDOWSCE**<br/>
WINDOWSCE alt sistemi, uygulamanın Windows CE çekirdek sürümü olan bir cihazda çalıştırmak için tasarlanan olduğunu gösterir. Çekirdek sürümleri şunlardır PocketPC, Windows Mobile, Windows Phone 7, Windows CE V 1.0-6.0 R3 ve Windows Embedded Compact 7.

İsteğe bağlı `major` ve `minor` değerler, belirtilen alt sistemin gerekli en düşük sürümünü belirtir:

- Sürüm numarasının tamamı (ondalık noktanın solundaki bölüm) tarafından temsil edilir `major` .

- Sürüm numarasının kesirli bölümü — ondalık noktanın sağ tarafında bulunan bölüm ile temsil edilir `minor` .

- `major`Ve değerleri `minor` 0 ile 65.535 arasında olmalıdır.

Alt sistem seçimi programın varsayılan başlangıç adresini etkiler. Daha fazla bilgi için bkz. [/Entry (giriş noktası simgesi)](entry-entry-point-symbol.md), bağlayıcı/entry:*işlev* seçeneği.

Her alt sistem için birincil ve ikincil sürüm numaraları için en düşük ve varsayılan değerler de dahil olmak üzere daha fazla bilgi için [/Subsystem](subsystem-specify-subsystem.md) bağlayıcı seçeneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)
