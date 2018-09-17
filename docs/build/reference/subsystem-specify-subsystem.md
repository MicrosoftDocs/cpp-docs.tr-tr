---
title: -SUBSYSTEM (alt sistemi belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
dev_langs:
- C++
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75e4612104fdc57fd1442f1a35efbf317a60310d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717099"
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM (Alt Sistemi Belirt)

```
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|
            POSIX|WINDOWS)
            [,major[.minor]]
```

## <a name="arguments"></a>Arguments

**BOOT_APPLICATION**<br/>
Windows önyükleme ortamında çalışan bir uygulama. Önyükleme uygulamaları hakkında daha fazla bilgi için bkz. [hakkında BCD](/previous-versions/windows/desktop/bcd/about-bcd).

**KONSOLU**<br/>
Win32 karakter modu uygulaması. İşletim sistemi konsol uygulamaları için bir konsol sağlar. Varsa `main` veya `wmain` yerel kod için tanımlanır `int main(array<String ^> ^)` yönetilen kod için tanımlanır veya uygulamanın tamamen yapı `/clr:safe`, KONSOL varsayılandır.

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
Genişletilebilir Bellenim Arabirimi alt sistemler. EFI belirtimi daha fazla bilgi için bkz. Örnekler için Intel Web sitesine bakın. En düşük sürümü ve varsayılan sürüm 1.0 ' dir.

**YEREL**<br/>
Windows NT Çekirdek modu sürücüleri. Bu seçenek genelde Windows sistem bileşenleri için ayrılmıştır. Varsa [/DRIVER: WDM](../../build/reference/driver-windows-nt-kernel-mode-driver.md) belirtilirse, yerel varsayılandır.

**POSIX**<br/>
Windows NT'de POSIX alt sistemi ile çalışan uygulama.

**WINDOWS**<br/>
Uygulama kullanıcı etkileşimi için kendi pencerelerini oluşturduğundan konsol, büyük olasılıkla gerektirmez. Varsa `WinMain` veya `wWinMain` yerel kod için tanımlanır veya `WinMain(HISTANCE *, HINSTANCE *, char *, int)` veya `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` tanımlanan yönetilen kod için WINDOWS varsayılandır.

*Ana* ve *küçük*<br/>
(İsteğe bağlı) Alt sistemin gerekli en düşük sürümü belirtin. Bağımsız değişkenler, 0 ile 65.535 aralığındaki ondalık sayılardır. Daha fazla bilgi için açıklamalara bakın. Sürüm numaraları için hiçbir üst sınırları vardır.

## <a name="remarks"></a>Açıklamalar

**/Subsystem** seçeneği, yürütülebilir dosya için ortamı belirtir.

Alt sistem seçimi giriş noktası sembolünü (veya giriş noktası işlevini) etkiler, bağlayıcı seçer.

Varsayılan ve isteğe bağlı en az *ana* ve *küçük* alt sistemler için sürüm numaraları aşağıdaki gibidir.

|Alt sistem|Minimum|Varsayılan|
|---------------|-------------|-------------|
|BOOT_APPLICATION|1.0|1.0|
|KONSOLU|(x 86) 5.01 (x 64) 5.02 6.02 (ARM)|(x86, x64) 6.00 6.02 (ARM)|
|WINDOWS|(x 86) 5.01 (x 64) 5.02 6.02 (ARM)|(x86, x64) 6.00 6.02 (ARM)|
|Yerel (ile sürücü: WDM)|(x 86) 1,00 1.10 (x64, ARM)|(x 86) 1,00 1.10 (x64, ARM)|
|Yerel (olmadan/DRIVER: WDM)|(x 86) 4.00 (x 64) 5.02 6.02 (ARM)|(x 86) 4.00 (x 64) 5.02 6.02 (ARM)|
|POSIX|1.0|19.90|
|EFI_APPLICATION, EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1.0|1.0|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Bağlayıcı klasörü seçin.

1. Seçin **sistem** özellik sayfası.

1. Değiştirme `SubSystem` özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)