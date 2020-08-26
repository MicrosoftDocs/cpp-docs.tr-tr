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
ms.openlocfilehash: 5639344ede4007bd66a3d51043f4acb423426b94
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842981"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Windows NT Çekirdek Modu Sürücüsü)

>/DRıVER [: UPONLY |: WDM]

## <a name="remarks"></a>Açıklamalar

Windows NT Çekirdek modu sürücüsü oluşturmak için **/Driver** bağlayıcı seçeneğini kullanın.

**/DRIVER: UPONLY** , bağlayıcının tek IŞLEMCILI (up) bir sürücü olduğunu belirtmek için çıkış üstbilgisindeki özelliklere **IMAGE_FILE_UP_SYSTEM_ONLY** bitini eklemesine neden olur. İşletim sistemi, çok işlemcili (MP) bir sisteme bir UP sürücüsü yüklemeyi reddeder.

**/DRIVER: WDM** , bağlayıcının isteğe bağlı üstbilginin dllözellikler alanındaki **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** bitini ayarlamaya neden olur.

**/Driver** belirtilmemişse, bu bitler bağlayıcı tarafından belirlenmez.

**/DRIVER** belirtilmişse:

- **/Fixed: No** etkin. Daha fazla bilgi için bkz. [/Fixed (sabit temel adres)](fixed-fixed-base-address.md).

- Çıkış dosyasının uzantısı. sys olarak ayarlanır. Varsayılan dosya adını ve uzantıyı değiştirmek için **/Out** kullanın. Daha fazla bilgi için bkz. [/Out (çıktı dosyası adı)](out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Sistem** Özellik sayfasına tıklayın.

1. **Sürücü** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. [VCLinkerTool. Driver özelliği](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
