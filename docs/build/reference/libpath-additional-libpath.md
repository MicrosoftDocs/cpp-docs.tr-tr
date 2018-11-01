---
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
ms.openlocfilehash: 40662e77faf03de8e5ef0abf334f4ec7be69c3ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615157"
---
# <a name="libpath-additional-libpath"></a>/LIBPATH (Ek Libpath)

```
/LIBPATH:dir
```

## <a name="parameters"></a>Parametreler

*dizini*<br/>
Bir yol belirtir LIB ortam seçeneğinde belirtilen yolu arar önce bağlayıcı arar.

## <a name="remarks"></a>Açıklamalar

/ Libpath seçeneği, kullanıcının ortam kitaplık yolunu geçersiz kılmak için kullanın. Bağlayıcı bu seçeneği tarafından belirtilen yoldaki ilk arama ve LIB ortam değişkeninde belirtilen yolda arayın. Yalnızca bir dizine, girdiğiniz her/Libpath seçeneği belirtebilirsiniz. Birden fazla dizine belirtmek istiyorsanız, birden çok/Libpath seçeneği belirtmeniz gerekir. Bağlayıcı, ardından sırayla belirtilen dizinleri arar.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **genel** özellik sayfası.

1. Değiştirme **ek kitaplık dizinleri** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)