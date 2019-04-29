---
title: /WINMDFILE (winmd Dosyası Belirtin)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
ms.openlocfilehash: 5d24d1d1aad8442f549dcb1aa4bd6414070c282c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316489"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (winmd Dosyası Belirtin)

Tarafından oluşturulan Windows çalışma zamanı meta veri (.winmd) çıktı dosyasının dosya adını belirtir [/WINMD](winmd-generate-windows-metadata.md) bağlayıcı seçeneği.

```
/WINMDFILE:filename
```

## <a name="remarks"></a>Açıklamalar

Belirtilen değeri kullanın `filename` varsayılan .winmd dosyası adını geçersiz kılacak (`binaryname`.winmd). İçin ".winmd" eklemeyin fark `filename`.  Birden çok değer üzerinde listeleniyorsa **/wınmdfıle** komut satırı, sonuncu öncelik alır.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **Windows meta verileri** özellik sayfası.

1. İçinde **Windows meta veri dosyası** kutusuna, dosya konumu girin.

## <a name="see-also"></a>Ayrıca bkz.

[/WINMD (Windows Meta Verileri Oluşturun)](winmd-generate-windows-metadata.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
