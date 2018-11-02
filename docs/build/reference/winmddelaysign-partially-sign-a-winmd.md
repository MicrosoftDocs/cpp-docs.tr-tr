---
title: /WINMDDELAYSIGN (winmd Dosyasını Kısmen İmzalayın)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 367dbe0e638e3748f259f22c1e3536bbd7398272
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606004"
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