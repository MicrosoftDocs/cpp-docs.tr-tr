---
description: Şu konuda daha fazla bilgi edinin:/DELAYLOAD (yük Içeri aktarmayı geciktir)
title: /DELAYLOAD (Yükü İçe Aktarmayı Geciktir)
ms.date: 11/04/2016
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
ms.openlocfilehash: 9f6a91a102b66a16896d51b960d44273a7935d79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201501"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (Yükü İçe Aktarmayı Geciktir)

> **/Delayload:**_DLL adı_

## <a name="parameters"></a>Parametreler

*dll*<br/>
Yük geciktirmesini istediğiniz DLL 'in adı.

## <a name="remarks"></a>Açıklamalar

/DELAYLOAD seçeneği, tarafından belirtilen DLL 'nin `dllname` yalnızca program tarafından bu DLL 'deki bir işleve olan ilk çağrıda yüklenmesine neden olur. Daha fazla bilgi için bkz. [Delay-Loaded dll 'ler Için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md). Bu seçeneği, seçtiğiniz sayıda dll 'yi belirtmek için gereken kadar çok kez kullanabilirsiniz. Programınızı bağladığınızda delayimp. lib kullanmanız gerekir veya kendi gecikme Yükleme Yardımcısı işlevinizi uygulayabilirsiniz.

[/Delay](delay-delay-load-import-settings.md) seçeneği, Gecikmeli yüklenen her dll için bağlama ve yükleme seçeneklerini belirtir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasöründe **giriş** özellik sayfasını seçin.

1. **Yüklenen dll 'Leri geciktir** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
