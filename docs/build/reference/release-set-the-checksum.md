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
ms.openlocfilehash: 1dc09b38beeb763733f8fa6a8ffa972059b30e03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318933"
---
# <a name="release-set-the-checksum"></a>/RELEASE (Sağlama Toplamını Ayarla)

```
/RELEASE
```

## <a name="remarks"></a>Açıklamalar

/ Release seçeneği, .exe dosyasının üst bilgisinde sağlama toplamını ayarlar.

İşletim sistemi sağlama toplamı için cihaz sürücüleri gerektirir. Gelecekteki işletim sistemleriyle uyumluluğu sağlamak için yayın sürümleri, aygıt sürücüsü için sağlama toplamı ayarlayın.

/ Release seçeneği varsayılan olarak ayarlanır, [natıve](subsystem-specify-subsystem.md) seçeneği belirtildi.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **kümesi sağlama toplamı** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
