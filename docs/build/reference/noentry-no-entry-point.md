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
ms.openlocfilehash: c750fd94e21eec39a25acf216a452faaa277bf7c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811458"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (Giriş Noktası Yok)

```
/NOENTRY
```

## <a name="remarks"></a>Açıklamalar

/ NOENTRY seçeneği, yürütülebilir kod içermeyen bir kaynak DLL'si oluşturmak için gereklidir. Daha fazla bilgi için [Resource-Only DLL oluşturma](../creating-a-resource-only-dll.md).

BAĞLANTI bir başvuru önleme için bu seçeneği kullanın `_main` DLL içine.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **Hayır giriş noktası** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Yalnızca Kaynak DLL Oluşturma](../creating-a-resource-only-dll.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
