---
description: Şu konuda daha fazla bilgi edinin:/LıBPATH (ek libpath)
title: /LIBPATH (Ek Libpath)
ms.date: 11/04/2016
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
ms.openlocfilehash: 5db7a0f80cb741a65bac5a4dbb7fd79e28b67459
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191036"
---
# <a name="libpath-additional-libpath"></a>/LIBPATH (Ek Libpath)

```
/LIBPATH:dir
```

## <a name="parameters"></a>Parametreler

*öğesini*<br/>
Bağlayıcının LıB Environment seçeneğinde belirtilen yolu aramadan önce arayacağını belirten bir yol belirtir.

## <a name="remarks"></a>Açıklamalar

Ortam kitaplığı yolunu geçersiz kılmak için/LIBPATH seçeneğini kullanın. Bağlayıcı öncelikle bu seçenekle belirtilen yolda arama yapılır ve sonra LıB ortam değişkeninde belirtilen yolda arama yapılır. Girdiğiniz her/LIBPATH seçeneği için yalnızca bir dizin belirtebilirsiniz. Birden fazla dizin belirtmek istiyorsanız, birden çok/LIBPATH seçeneği belirtmeniz gerekir. Bağlayıcı daha sonra belirtilen dizinlerde sırayla arama yapılır.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Genel** Özellik sayfasına tıklayın.

1. **Ek kitaplık dizinleri** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
