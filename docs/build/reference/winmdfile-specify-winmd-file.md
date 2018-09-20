---
title: -WINMDFILE (winmd dosyası belirtin) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
dev_langs:
- C++
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d34bdfd2d80690efae8efbc1f95ba0c50a530af3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425790"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (winmd Dosyası Belirtin)

Tarafından oluşturulan Windows çalışma zamanı meta veri (.winmd) çıktı dosyasının dosya adını belirtir [/WINMD](../../build/reference/winmd-generate-windows-metadata.md) bağlayıcı seçeneği.

```
/WINMDFILE:filename
```

## <a name="remarks"></a>Açıklamalar

Belirtilen değeri kullanın `filename` varsayılan .winmd dosyası adını geçersiz kılacak (`binaryname`.winmd). İçin ".winmd" eklemeyin fark `filename`.  Birden çok değer üzerinde listeleniyorsa **/wınmdfıle** komut satırı, sonuncu öncelik alır.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **Windows meta verileri** özellik sayfası.

1. İçinde **Windows meta veri dosyası** kutusuna, dosya konumu girin.

## <a name="see-also"></a>Ayrıca Bkz.

[/WINMD (Windows Meta Verileri Oluşturun)](../../build/reference/winmd-generate-windows-metadata.md)<br/>
[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)