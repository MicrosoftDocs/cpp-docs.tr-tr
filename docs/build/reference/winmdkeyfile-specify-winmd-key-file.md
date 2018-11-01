---
title: /WINMDKEYFILE (winmd Anahtar Dosyası Belirtin)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKeyFile
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
ms.openlocfilehash: 076533278bb9b8ec2838cfb719bcb4df1784b258
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436797"
---
# <a name="winmdkeyfile-specify-winmd-key-file"></a>/WINMDKEYFILE (winmd Anahtar Dosyası Belirtin)

Bir anahtar veya bir Windows çalışma zamanı meta veri (.winmd) dosyasını imzalamak için bir anahtar çiftini belirtir.

```
/WINMDKEYFILE:filename
```

## <a name="remarks"></a>Açıklamalar

Benzer [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) bir .winmd dosyasına uygulanan bağlayıcı seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **Windows meta verileri** özellik sayfası.

1. İçinde **Windows meta verileri anahtar dosyası** kutusuna, dosya konumu girin.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)