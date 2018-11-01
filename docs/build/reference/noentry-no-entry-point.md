---
title: /NOENTRY (Giriş Noktası Yok)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
ms.openlocfilehash: fef4340fa4bb130ac54f4d5e66d4cd4d2f2a3049
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607371"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (Giriş Noktası Yok)

```
/NOENTRY
```

## <a name="remarks"></a>Açıklamalar

/ NOENTRY seçeneği, yürütülebilir kod içermeyen bir kaynak DLL'si oluşturmak için gereklidir. Daha fazla bilgi için [Resource-Only DLL oluşturma](../../build/creating-a-resource-only-dll.md).

BAĞLANTI bir başvuru önleme için bu seçeneği kullanın `_main` DLL içine.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **Hayır giriş noktası** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Yalnızca Kaynak DLL Oluşturma](../../build/creating-a-resource-only-dll.md)<br/>
[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)