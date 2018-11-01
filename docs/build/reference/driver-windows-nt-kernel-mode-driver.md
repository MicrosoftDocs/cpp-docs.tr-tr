---
title: /DRIVER (Windows NT Çekirdek Modu Sürücüsü)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
ms.openlocfilehash: 7e01cf8ba027fc2062d01173aca544fae4b937e3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656865"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Windows NT Çekirdek Modu Sürücüsü)

>/ DRIVER [: UPONLY |: WDM]

## <a name="remarks"></a>Açıklamalar

Kullanım **Driver/Driver** bir Windows NT Çekirdek modu sürücüsü oluşturmak için bağlayıcı seçeneği.

**/DRIVER:UPONLY** eklemek bağlayıcı neden **ımage_fıle_up_system_only** tek işlemcili (UP) sürücü olduğunu belirtmek için çıkış üst özelliklerine bit. İşletim sistemi, UP sürücüsünü çok işlemcili bir (MP) sistemi yüklenecek reddeder.

**/ DRIVER: WDM** ayarlanacak bağlayıcının neden **ımage_dllcharacterıstıcs_wdm_drıver** isteğe bağlı üst bilgi dllcharacteristics bit.

Varsa **Driver/Driver** belirtilmemişse, bu bit bağlayıcı tarafından ayarlı değil.

Varsa **Driver/Driver** belirtilir:

- **/ FIXED: No** etkindir. Daha fazla bilgi için [/FIXED (sabit temel adres)](../../build/reference/fixed-fixed-base-address.md).

- Çıkış dosyasının uzantısı .sys için ayarlanır. Kullanım **/OUT** varsayılan dosya adı ve uzantısını değiştirmek için. Daha fazla bilgi için [/OUT (çıktı dosyası adı)](../../build/reference/out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **sistem** özellik sayfası.

1. Değiştirme **sürücü** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: [VCLinkerTool.driver özelliği](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
