---
title: /SUBSYSTEM (Alt Sistemi Belirt)
ms.date: 11/04/2016
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
ms.openlocfilehash: ecda3443d0422af4d5ceec9282d86590c53af2f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318251"
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
Windows NT Çekirdek modu sürücüleri. Bu seçenek genelde Windows sistem bileşenleri için ayrılmıştır. Varsa [/DRIVER: WDM](driver-windows-nt-kernel-mode-driver.md) belirtilirse, yerel varsayılandır.

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
|KONSOLU|(x 86) 5.01 (x 64) 5.02 6.02 (ARM)|6.00 (x86, x64) 6.02 (ARM)|
|WINDOWS|(x 86) 5.01 (x 64) 5.02 6.02 (ARM)|6.00 (x86, x64) 6.02 (ARM)|
|Yerel (ile sürücü: WDM)|(x 86) 1,00 1.10 (x64, ARM)|(x 86) 1,00 1.10 (x64, ARM)|
|Yerel (olmadan/DRIVER: WDM)|(x 86) 4.00 (x 64) 5.02 6.02 (ARM)|(x 86) 4.00 (x 64) 5.02 6.02 (ARM)|
|POSIX|1.0|19.90|
|EFI_APPLICATION, EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1.0|1.0|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Bağlayıcı klasörü seçin.

1. Seçin **sistem** özellik sayfası.

1. Değiştirme `SubSystem` özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
