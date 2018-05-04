---
title: -DRIVER (Windows NT Çekirdek modu sürücüsü) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
dev_langs:
- C++
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66291391ed38c27ce7446eccc6fca227c7c2c2d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Windows NT Çekirdek Modu Sürücüsü)

>/ DRIVER [: UPONLY |: WDM]

## <a name="remarks"></a>Açıklamalar

Kullanım **/sürücü** bir Windows NT Çekirdek modu sürücüsü oluşturmak için bağlayıcı seçeneği.

**/DRIVER:UPONLY** eklemek bağlayıcı neden **IMAGE_FILE_UP_SYSTEM_ONLY** özelliklerinin tek işlemcili (UP) sürücüsü olduğunu belirtmek için çıkış üstbilgisinde bit. İşletim sistemi, çok işlemcili (MP) sisteminde yukarı sürücüsünü yüklemek reddeder.

**/DRIVER:WDM** ayarlamak bağlayıcı neden **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** isteğe bağlı başlığının DllCharacteristics alanına bit.

Varsa **/sürücü** belirtilmemişse, bu BITS bağlayıcı tarafından ayarlı değil.

Varsa **/sürücü** belirtilir:

- **/FIXED:NO** etkili olur. Daha fazla bilgi için bkz: [/FIXED (sabit temel adres)](../../build/reference/fixed-fixed-base-address.md).

- Çıkış dosyasının uzantısı .sys için ayarlanır. Kullanım **/OUT** varsayılan dosya adı ve uzantısı değiştirmek için. Daha fazla bilgi için bkz: [/OUT (çıktı dosyası adı)](../../build/reference/out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklatın **bağlayıcı** klasör.

1. Tıklatın **sistem** özellik sayfası.

1. Değiştirme **sürücü** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: [VCLinkerTool.driver özelliği](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
