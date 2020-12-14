---
description: Daha fazla bilgi edinin:/WINMDKEYCONTAINER (anahtar kapsayıcısını belirt)
title: /WINMDKEYCONTAINER (Tanımlayıcı Ad Anahtar Kapsayıcısı Belirtin)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
ms.openlocfilehash: 94b203c56b7724c2b2569ba22039da38c4501985
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258999"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (Tanımlayıcı Ad Anahtar Kapsayıcısı Belirtin)

Bir Windows meta veri (. winmd) dosyasını imzalamak için bir anahtar kapsayıcısı belirtir.

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>Açıklamalar

Bir (. winmd) dosyasına uygulanan [/keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md) bağlayıcı seçeneğine benzer.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörünü seçin.

1. **Windows meta verileri** özellik sayfasını seçin.

1. **Windows meta verileri anahtar kapsayıcısı** kutusuna konumu girin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
