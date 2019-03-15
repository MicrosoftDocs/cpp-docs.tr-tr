---
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
ms.openlocfilehash: e92b470b7b5e76b39371f333cbbda150e7f6e8c7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817653"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (Yükü İçe Aktarmayı Geciktir)

> **/ DELAYLOAD:**_dll adı_

## <a name="parameters"></a>Parametreler

*dll adı*<br/>
Yüklenmesinin ertelenmesini istediğiniz bir DLL'nin adı.

## <a name="remarks"></a>Açıklamalar

/ Delayload seçeneği tarafından belirtilen DLL'yi `dllname` yalnızca ilk çağrıda bir işlev DLL içindeki program tarafından yüklenecek. Daha fazla bilgi için [Delay-Loaded DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md). İstediğiniz sayıda DLL'yi belirtmek için gerekli sayıda bu seçeneği kullanabilirsiniz. Programınızın ya da kendi gecikme yük yardımcı işlevinizi uygulayabilirsiniz, Delayimp.lib kullanmanız gerekir.

[/DELAY](delay-delay-load-import-settings.md) seçeneği, bağlama ve yükleme seçenekleri Gecikmeli yüklenen her DLL için belirtir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. İçinde **bağlayıcı** klasörüne **giriş** özellik sayfası.

1. Değiştirme **yüklü DLL'leri Geciktir** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
