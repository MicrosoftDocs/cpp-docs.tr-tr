---
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
ms.openlocfilehash: 6a45e6caa94054d4d485476786ecc5149545ed8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478815"
---
# <a name="release-set-the-checksum"></a>/RELEASE (Sağlama Toplamını Ayarla)

```
/RELEASE
```

## <a name="remarks"></a>Açıklamalar

/ Release seçeneği, .exe dosyasının üst bilgisinde sağlama toplamını ayarlar.

İşletim sistemi sağlama toplamı için cihaz sürücüleri gerektirir. Gelecekteki işletim sistemleriyle uyumluluğu sağlamak için yayın sürümleri, aygıt sürücüsü için sağlama toplamı ayarlayın.

/ Release seçeneği varsayılan olarak ayarlanır, [natıve](../../build/reference/subsystem-specify-subsystem.md) seçeneği belirtildi.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **kümesi sağlama toplamı** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)