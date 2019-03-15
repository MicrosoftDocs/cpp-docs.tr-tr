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
ms.openlocfilehash: af7962a4b3b5805e7e0c4d59752254c8ade17f7b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814312"
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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
