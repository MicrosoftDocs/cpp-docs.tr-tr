---
title: -Wınmddelaysıgn (dosyasını kısmen imzalayın winmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
dev_langs:
- C++
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b31f6ae5baf9aadbb40b4b45f532b344b6b2e037
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723859"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (winmd Dosyasını Kısmen İmzalayın)

Kısmi bir Windows çalışma zamanı meta veri (.winmd) dosyasını imzalama dosyasında ortak anahtarı yerleştirerek sağlar.

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>Açıklamalar

Benzer [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) .winmd dosyasına uygulanan bağlayıcı seçeneği. Kullanım **/WINMDDELAYSIGN** .winmd dosyasında yalnızca ortak anahtar yerleştirmek istiyorsanız. Varsayılan olarak, bağlayıcı çalışır gibi **wınmddelaysıgn** belirtildi; diğer bir deyişle, bunun bir winmd dosyası oturum açmasını sağlamayan.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **Windows meta verileri** özellik sayfası.

1. İçinde **Windows meta verileri gecikmeli imza** aşağı açılan liste kutusunda, kullanmak istediğiniz seçeneği seçin.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)