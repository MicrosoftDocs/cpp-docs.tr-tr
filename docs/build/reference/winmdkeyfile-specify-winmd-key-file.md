---
title: -WINMDKEYFILE (winmd anahtar dosyası belirtin) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKeyFile
dev_langs:
- C++
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d688db3039681fc684e6344e4a27ae7a64544757
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714455"
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