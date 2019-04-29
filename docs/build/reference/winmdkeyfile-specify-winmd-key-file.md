---
title: /WINMDKEYFILE (winmd Anahtar Dosyası Belirtin)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKeyFile
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
ms.openlocfilehash: 4b0c847bc5be6c73b78af4aa15b0074c712cc840
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316463"
---
# <a name="winmdkeyfile-specify-winmd-key-file"></a>/WINMDKEYFILE (winmd Anahtar Dosyası Belirtin)

Bir anahtar veya bir Windows çalışma zamanı meta veri (.winmd) dosyasını imzalamak için bir anahtar çiftini belirtir.

```
/WINMDKEYFILE:filename
```

## <a name="remarks"></a>Açıklamalar

Benzer [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) bir .winmd dosyasına uygulanan bağlayıcı seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **Windows meta verileri** özellik sayfası.

1. İçinde **Windows meta verileri anahtar dosyası** kutusuna, dosya konumu girin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
