---
description: Şu konuda daha fazla bilgi edinin:/WINMDKEYFILE (WinMD anahtar dosyası belirtin)
title: /WINMDKEYFILE (winmd Anahtar Dosyası Belirtin)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKeyFile
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
ms.openlocfilehash: 0e7b23de62613f51c3824b107e55180bb54780d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258908"
---
# <a name="winmdkeyfile-specify-winmd-key-file"></a>/WINMDKEYFILE (winmd Anahtar Dosyası Belirtin)

Bir Windows Çalışma Zamanı meta veri (. winmd) dosyasını imzalamak için bir anahtar veya anahtar çiftini belirtir.

```
/WINMDKEYFILE:filename
```

## <a name="remarks"></a>Açıklamalar

Bir. winmd dosyasına uygulanan [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) bağlayıcı seçeneğine benzer.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörünü seçin.

1. **Windows meta verileri** özellik sayfasını seçin.

1. **Windows meta verileri anahtar dosyası** kutusuna dosya konumunu girin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
