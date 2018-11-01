---
title: /FORCE (Dosya Çıktısını Zorla)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
ms.openlocfilehash: 5555a76cc792c15bea9c6c393debbd0fb38e30e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445663"
---
# <a name="force-force-file-output"></a>/FORCE (Dosya Çıktısını Zorla)

```
/FORCE:[MULTIPLE|UNRESOLVED]
```

## <a name="remarks"></a>Açıklamalar

/ Force seçeneği geçerli bir .exe dosyası oluşturmak için söyler veya DLL sembole başvurulduğunda ancak bile tanımlanan veya tanımlı çarpın.

/ Force seçeneği isteğe bağlı bağımsız değişken alabilir:

- BAĞLANTI bir sembol için birden fazla tanım bulursa olup olmadığını bulmadığında çıkış dosyası oluşturmak için/Force: multıple kullanın.

- / Force kullanın: tanımsız bir sembol bağlantı bulursa olup olmadığını bir çıkış dosyası oluşturmak için. / FORCE: ÇÖZÜMLENMEMİŞ giriş noktası sembolü çözümlenmemiş ise göz ardı edilir.

/ Bağımsız değişken olmadan FORCE, hem birden çok anlamına gelir ve çözümlenmemiş.

Bu seçenekle oluşturulan bir dosya, beklendiği gibi çalışmayabilir. / Force seçeneği belirtildiğinde bağlayıcı artımlı olarak bağlayacaksınız değil.

Bir modül ile derlenmişse **/CLR**, **/FORCE** görüntü oluşturmaz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)