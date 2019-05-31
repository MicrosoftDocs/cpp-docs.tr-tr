---
title: /SUBSYSTEM
ms.date: 11/04/2016
f1_keywords:
- /subsystem
helpviewer_keywords:
- /SUBSYSTEM editbin option
- -SUBSYSTEM editbin option
- SUBSYSTEM editbin option
ms.assetid: 515e4cdf-3cc4-4659-8764-1f2757b49215
ms.openlocfilehash: e67ec57c3a8d74fdd97a94ed04c29cad53af1ea5
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450735"
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

**BOOT_APPLICATION**<br/>
Windows önyükleme ortamında çalışan bir uygulama. Önyükleme uygulamaları hakkında daha fazla bilgi için bkz. [BCD WMI sağlayıcısı hakkında](/previous-versions/windows/desktop/bcd/about-bcd).

**KONSOLU**<br/>
Windows karakter modu uygulaması. İşletim sistemi konsol uygulamaları için bir konsol sağlar.

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
Genişletilebilir Bellenim Arabirimi (EFI) görüntüsü

EFI alt seçenekleri, Genişletilebilir Bellenim Arabirimi ortamında çalışan yürütülebilir resimleri açıklar. Bu ortam genellikle donanımla birlikte sağlanır ve işletim sistemi yüklenmeden önce yürütülür. EFI resim türleri arasındaki başlıca farklar şunlardır: görüntünün yüklendiği bellek konumu ve resim çağrısı döndüğünde alınmış eylemi. Denetimi geri döndüğünde, efı_applıcatıon görüntüsü kaldırılır. Efı_boot_servıce_drıver veya efı_runtıme_drıver yalnızca denetim bir hata koduyla döndüğünde kaldırılır. Efı_rom görüntüsü ROM'dan yürütülür. Daha fazla bilgi için bakın [birleşik EFI Forumu](https://www.uefi.org/) Web sitesi.

**YEREL**<br/>
Bir alt sistem ortamı olmadan çalışan kod — Örneğin, kernel modlu cihaz sürücüleri ve yerel sistem işlemleri. Bu seçenek genelde Windows Sistem özellikleri için ayrılmıştır.

**POSIX**<br/>
Windows, POSIX alt sisteminde çalışan bir uygulama.

**WINDOWS**<br/>
Windows grafik ortamında çalışan bir uygulama. Bu, hem Masaüstü uygulamaları hem de Evrensel Windows Platformu (UWP) uygulamaları içerir.

**WINDOWSCE**<br/>
WINDOWSCE alt sistemi, uygulamanın Windows CE çekirdeği sürümüne sahip bir cihazda çalıştırılacak amaçlandığını gösterir. Çekirdek sürümleri PocketPC, Windows Mobile, Windows Phone 7, Windows CE V1.0-6.0R3 ve Windows Embedded Compact 7 içerir.

İsteğe bağlı `major` ve `minor` değerleri belirtilen alt sistemin gerekli en düşük sürümü belirtin:

- Sürüm numarasının tam sayı bölümü — bölümü Ondalık ayırıcının solundaki — tarafından temsil edilen `major`.

- Sürüm numarasının kesirli bölümü — bölümü ondalık noktanın sağındaki — tarafından temsil edilen `minor`.

- Değerlerini `major` ve `minor` 0 ile 65.535 arasında olmalıdır.

Başlangıç adresi program için varsayılan alt sistem seçimi etkiler. Daha fazla bilgi için [/Entry (giriş noktası simgesi)](entry-entry-point-symbol.md), bağlayıcı/Entry:*işlevi* seçeneği.

Her alt sistemin büyük ve küçük sürüm numaraları için minimum ve varsayılan değerler dahil olmak üzere daha fazla bilgi için bkz. [/Subsystem](subsystem-specify-subsystem.md) bağlayıcı seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)
