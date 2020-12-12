---
description: Daha fazla bilgi için bkz./RELEASE (sağlama toplamını ayarla)
title: /RELEASE (Sağlama Toplamını Ayarla)
ms.date: 11/04/2016
f1_keywords:
- /release
- VC.Project.VCLinkerTool.SetChecksum
helpviewer_keywords:
- -RELEASE linker option
- /RELEASE linker option
- checksum setting
- RELEASE linker option
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
ms.openlocfilehash: ed1e55dffb02ace26e91e262bd3e9514f056196e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225329"
---
# <a name="release-set-the-checksum"></a>/RELEASE (Sağlama Toplamını Ayarla)

```
/RELEASE
```

## <a name="remarks"></a>Açıklamalar

/RELEASE seçeneği,. exe dosyasının üst bilgisindeki sağlama toplamını ayarlar.

İşletim sistemi cihaz sürücüleri için sağlama toplamı gerektirir. Gelecekteki işletim sistemleriyle uyumluluğu sağlamak için cihaz sürücülerinizin yayın sürümleri için sağlama toplamını ayarlayın.

/RELEASE seçeneği, [/Subsystem: NATIVE](subsystem-specify-subsystem.md) seçeneği belirtildiğinde varsayılan olarak ayarlanır.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Gelişmiş** Özellik sayfasına tıklayın.

1. **Set checksum** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
