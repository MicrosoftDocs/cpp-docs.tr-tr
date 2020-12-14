---
description: Daha fazla bilgi edinin:/SUBSYSTEM (alt sistemi belirt)
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
ms.openlocfilehash: 18a8ad549cc4aa1e143e43619d549c9eb7ae7324
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236249"
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
Windows önyükleme ortamında çalışan bir uygulama. Önyükleme uygulamaları hakkında daha fazla bilgi için bkz. [BCD hakkında](/previous-versions/windows/desktop/bcd/about-bcd).

**KONSOLA**<br/>
Win32 karakter modu uygulaması. İşletim sistemi konsol uygulamaları için bir konsol sağlar. `main`Veya `wmain` yerel kod için tanımlanmışsa, `int main(array<String ^> ^)` yönetilen kod için tanımlanır veya uygulamayı kullanarak tamamen oluşturursanız `/clr:safe` , konsol varsayılandır.

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
Genişletilebilir Bellenim Arabirimi alt sistemleri. Daha fazla bilgi için EFı belirtimine bakın. Örnekler için bkz. Intel Web sitesi. En düşük sürüm ve varsayılan sürüm 1,0 ' dir.

**Yerel**<br/>
Windows NT için çekirdek modu sürücüleri. Bu seçenek, genellikle Windows sistem bileşenleri için ayrılmıştır. [/DRIVER: WDM](driver-windows-nt-kernel-mode-driver.md) BELIRTILMIŞSE, yerel varsayılandır.

**OF**<br/>
Windows NT 'de POSIX alt sistemi ile çalışan uygulama.

**PENCERELERIN**<br/>
Uygulama, büyük olasılıkla Kullanıcı etkileşimi için kendi pencerelerini oluşturduğundan, bir konsol gerektirmez. `WinMain`Veya `wWinMain` yerel kod için tanımlandıysa ya da `WinMain(HISTANCE *, HINSTANCE *, char *, int)` `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` yönetilen kod için tanımlandıysa, WINDOWS varsayılandır.

*büyük* ve *küçük*<br/>
Seçim Alt sistemin gerekli en düşük sürümünü belirtin. Bağımsız değişkenler 0 ile 65.535 aralığındaki ondalık sayılardır. Daha fazla bilgi için bkz. açıklamalar. Sürüm numaraları için üst sınır yoktur.

## <a name="remarks"></a>Açıklamalar

**/Subsystem** seçeneği yürütülebilir dosyanın ortamını belirtir.

Alt sistem seçimi, bağlayıcının seçim kullanacağı giriş noktası sembolünü (veya giriş noktası işlevini) etkiler.

Alt sistemler için isteğe bağlı minimum ve varsayılan *büyük* ve *küçük* sürüm numaraları aşağıdaki gibidir.

|Sistemin|Minimum|Varsayılan|
|---------------|-------------|-------------|
|BOOT_APPLICATION|1,0|1,0|
|KONSOLA|5,01 (x86) 5,02 (x64) 6,02 (ARM)|6,00 (x86, x64) 6,02 (ARM)|
|PENCERELERIN|5,01 (x86) 5,02 (x64) 6,02 (ARM)|6,00 (x86, x64) 6,02 (ARM)|
|Yerel (sürücü: WDM)|1,00 (x86) 1,10 (x64, ARM)|1,00 (x86) 1,10 (x64, ARM)|
|Yerel (/DRıVER: WDM olmadan)|4,00 (x86) 5,02 (x64) 6,02 (ARM)|4,00 (x86) 5,02 (x64) 6,02 (ARM)|
|OF|1,0|19,90|
|EFI_APPLICATION, EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1,0|1,0|

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Bağlayıcı klasörünü seçin.

1. **Sistem** özellik sayfasını seçin.

1. Özelliği değiştirin `SubSystem` .

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
