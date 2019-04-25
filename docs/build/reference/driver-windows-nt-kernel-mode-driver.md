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
ms.openlocfilehash: ab7253d7e386bf385bcb3a586c5e0e1c1e860694
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293114"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Windows NT Çekirdek Modu Sürücüsü)

>/ DRIVER [: UPONLY |: WDM]

## <a name="remarks"></a>Açıklamalar

Kullanım **Driver/Driver** bir Windows NT Çekirdek modu sürücüsü oluşturmak için bağlayıcı seçeneği.

**/DRIVER:UPONLY** eklemek bağlayıcı neden **ımage_fıle_up_system_only** tek işlemcili (UP) sürücü olduğunu belirtmek için çıkış üst özelliklerine bit. İşletim sistemi, UP sürücüsünü çok işlemcili bir (MP) sistemi yüklenecek reddeder.

**/ DRIVER: WDM** ayarlanacak bağlayıcının neden **ımage_dllcharacterıstıcs_wdm_drıver** isteğe bağlı üst bilgi dllcharacteristics bit.

Varsa **Driver/Driver** belirtilmemişse, bu bit bağlayıcı tarafından ayarlı değil.

Varsa **Driver/Driver** belirtilir:

- **/ FIXED: No** etkindir. Daha fazla bilgi için [/FIXED (sabit temel adres)](fixed-fixed-base-address.md).

- Çıkış dosyasının uzantısı .sys için ayarlanır. Kullanım **/OUT** varsayılan dosya adı ve uzantısını değiştirmek için. Daha fazla bilgi için [/OUT (çıktı dosyası adı)](out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **sistem** özellik sayfası.

1. Değiştirme **sürücü** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: [VCLinkerTool.driver özelliği](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
