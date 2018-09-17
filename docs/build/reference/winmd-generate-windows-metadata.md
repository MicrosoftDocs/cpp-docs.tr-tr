---
title: -WINMD (Windows meta verileri oluşturun) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25b8b34e55fc0814653f4c44be50e545633be373
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705737"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows Meta Verileri Oluşturun)

Bir Windows çalışma zamanı meta veri (.winmd) dosyasının oluşturulmasını etkinleştirir.

```
/WINMD[:{NO|ONLY}]
```

## <a name="remarks"></a>Açıklamalar

**/ WINMD**<br/>
Evrensel Windows platformu uygulamaları için varsayılan ayar. Bağlayıcı, ikili yürütülebilir dosyasının hem .winmd meta veri dosyası oluşturur.

**/WINMD:NO**<br/>
Bağlayıcı, yalnızca ikili yürütülebilir dosya, ancak bir .winmd dosyası oluşturur.

**/ WINMD: YALNIZCA**<br/>
Bağlayıcı, yalnızca .winmd dosyası, ancak değil ikili yürütülebilir dosya oluşturur.

Varsayılan olarak, çıktı dosyası adını formundadır `binaryname`.winmd. Farklı bir dosya adı belirtmek için kullanın [/wınmdfıle](../../build/reference/winmdfile-specify-winmd-file.md) seçeneği.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **Windows meta verileri** özellik sayfası.

1. İçinde **Windows meta verileri oluşturma** aşağı açılan liste kutusunda, kullanmak istediğiniz seçeneği seçin.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)