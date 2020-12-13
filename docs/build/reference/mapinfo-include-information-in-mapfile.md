---
description: :/MAPıNFO hakkında daha fazla bilgi edinin (mapfile içindeki bilgileri dahil et)
title: /MAPINFO (Bilgileri Eşlem Dosyasına Dahil Et)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.MapLines
- VC.Project.VCLinkerTool.MapInfoFixups
- VC.Project.VCLinkerTool.MapExports
- /mapinfo
helpviewer_keywords:
- /MAPINFO linker option
- MAPINFO linker option
- -MAPINFO linker option
ms.assetid: 533d2bce-f9b7-4fea-ae1c-0b4864c9d10b
ms.openlocfilehash: 5cf785182bd91923c3398d542d7e60d9afdb4a4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137910"
---
# <a name="mapinfo-include-information-in-mapfile"></a>/MAPINFO (Bilgileri Eşlem Dosyasına Dahil Et)

```
/MAPINFO:EXPORTS
```

## <a name="remarks"></a>Açıklamalar

/MAPıNFO seçeneği, bağlayıcıya, [/Map](map-generate-mapfile.md) seçeneğini belirtirseniz oluşturulan bir mapfile öğesine belirtilen bilgileri dahil etmek üzere söyler.  Dışarı aktarmalar, bağlayıcıya dışarı aktarılan işlevleri eklemesini söyler.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Hata ayıklama** Özellik sayfasına tıklayın.

1. **Eşleme dışa aktarma** özelliklerini değiştirme:

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapExports%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
