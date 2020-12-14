---
description: Daha fazla bilgi edinin:/NOENTRY (giriş noktası yok)
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
ms.openlocfilehash: c3d1f725a4e185a052d443010894ff2dc2261675
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196691"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (Giriş Noktası Yok)

```
/NOENTRY
```

## <a name="remarks"></a>Açıklamalar

Bir çalıştırılabilir kod içermeyen yalnızca kaynak DLL oluşturmak için/NOENTRY seçeneği gereklidir. Daha fazla bilgi için bkz. [Resource-Only dll oluşturma](../creating-a-resource-only-dll.md).

BAĞLANTıNıN DLL 'ye başvuru bağlamasını engellemek için bu seçeneği kullanın `_main` .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörünü seçin.

1. **Gelişmiş** özellik sayfasını seçin.

1. **Giriş noktası yok** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Resource-Only DLL oluşturma](../creating-a-resource-only-dll.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
