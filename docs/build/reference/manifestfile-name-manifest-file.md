---
description: :/MANIFESTFILE (ad bildirim dosyası) hakkında daha fazla bilgi
title: /MANIFESTFILE (Bildirim Dosyasını Adlandır)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ManifestFile
helpviewer_keywords:
- MANIFESTFILE linker option
- -MANIFESTFILE linker option
- /MANIFESTFILE linker option
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
ms.openlocfilehash: a0d3a4ba1d17c4aa8c97cb09cc768e614e46c864
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138027"
---
# <a name="manifestfile-name-manifest-file"></a>/MANIFESTFILE (Bildirim Dosyasını Adlandır)

```
/MANIFESTFILE:filename
```

## <a name="remarks"></a>Açıklamalar

/MANIFESTFILE bildirim dosyasının varsayılan adını değiştirmenize olanak sağlar.  Bildirim dosyasının varsayılan adı. manifest eklenmiş dosya adıdır.

/Manifest ile de bağlantı görmüyorsanız/MANIFESTFILE hiçbir etkiye sahip olmayacaktır. [](manifest-create-side-by-side-assembly-manifest.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünü genişletin.

1. **Bağlayıcı** düğümünü genişletin.

1. **Bildirim dosyası** özellik sayfasını seçin.

1. **Bildirim dosyası** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
