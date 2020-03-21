---
title: /FORCE (Dosya Çıktısını Zorla)
ms.date: 07/19/2019
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
ms.openlocfilehash: d1d85174290faa95e73c63a25f7d80c554e83ace
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079627"
---
# <a name="force-force-file-output"></a>/FORCE (Dosya Çıktısını Zorla)

```
/FORCE:[MULTIPLE|UNRESOLVED]
```

## <a name="remarks"></a>Açıklamalar

/FORCE seçeneği, bir sembol başvuruluyorsa ancak tanımlanmadığı ya da tanımlanmış çarpma olsa bile, bağlayıcıya geçerli bir. exe dosyası veya DLL oluşturmasını söyler.

/FORCE seçeneği isteğe bağlı bir bağımsız değişken alabilir:

- BAĞLANTıNıN bir sembol için birden fazla tanım bulup bulmadığını bir çıkış dosyası oluşturmak için/FORCE: MULTIPLE kullanın.

- BAĞLANTıNıN tanımsız bir simge bulup bulmadığını bir çıkış dosyası oluşturmak için/FORCE: ÇÖZÜMLENMEMIŞ kullanın. /FORCE: giriş noktası simgesi çözülmedi ise ÇÖZÜMLENMEMIŞ yok sayılır.

Bağımsız değişken içermeyen/FORCE, hem birden çok hem de çözülmemiş anlamına gelir.

Bu seçenekle oluşturulan bir dosya beklendiği gibi çalışmayabilir. /FORCE seçeneği belirtildiğinde bağlayıcı artımlı olarak bağlantı etmez.

Bir modül **/clr**ile derlenirse **/Force** bir görüntü oluşturmaz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. **Çözüm Gezgini** ' de projeye sağ tıklayın ve **Özellikler**' i seçin.

1. **Bağlayıcı** klasörüne tıklayın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. Seçeneği **ek seçenekler** kutusuna yazın.

Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
