---
title: /MANIFESTFILE (Bildirim Dosyasını Adlandır)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ManifestFile
helpviewer_keywords:
- MANIFESTFILE linker option
- -MANIFESTFILE linker option
- /MANIFESTFILE linker option
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
ms.openlocfilehash: 9839665c3d74fd9d60afd21a825ffbdb752c7b00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656176"
---
# <a name="manifestfile-name-manifest-file"></a>/MANIFESTFILE (Bildirim Dosyasını Adlandır)

```
/MANIFESTFILE:filename
```

## <a name="remarks"></a>Açıklamalar

/ MANIFESTFILE, bildirim dosyasının varsayılan adını değiştirmenizi sağlar.  Dosya adına .manifest bildirim dosyasının varsayılan addır.

/ MANIFESTFILE, herhangi bir etkisi olacaktır, siz de ile bağlamazsanız [/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **bildirim dosyası** özellik sayfası.

1. Değiştirme **bildirim dosyası** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)