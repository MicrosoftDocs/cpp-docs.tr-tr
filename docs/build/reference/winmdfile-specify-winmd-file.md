---
description: Şu konuda daha fazla bilgi edinin:/WINMDFILE (WinMD dosyası belirtin)
title: /WINMDFILE (winmd Dosyası Belirtin)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
ms.openlocfilehash: fd10768c494bbedfbe650e0f0e3e72e8a062cdc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259025"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (winmd Dosyası Belirtin)

[/Winmd](winmd-generate-windows-metadata.md) bağlayıcı seçeneği tarafından oluşturulan Windows çalışma zamanı meta veri (. winmd) çıkış dosyasının dosya adını belirtir.

```
/WINMDFILE:filename
```

## <a name="remarks"></a>Açıklamalar

`filename`Varsayılan. winmd dosya adını (. winmd) geçersiz kılmak için içinde belirtilen değeri kullanın `binaryname` . '. Winmd ' öğesine eklemediğine dikkat edin `filename` .  **/WinMDFile** komut satırında birden çok değer listeleniyorsa, en son bir öncelik alır.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörünü seçin.

1. **Windows meta verileri** özellik sayfasını seçin.

1. **Windows meta verileri dosyası** kutusuna dosya konumunu girin.

## <a name="see-also"></a>Ayrıca bkz.

[/WINMD (Windows meta verileri oluştur)](winmd-generate-windows-metadata.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
