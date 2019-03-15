---
title: /WINMDDELAYSIGN (winmd Dosyasını Kısmen İmzalayın)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 5e6eab3fbc40543b634f03da826d3bd3477b9623
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57421479"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (winmd Dosyasını Kısmen İmzalayın)

Kısmi bir Windows çalışma zamanı meta veri (.winmd) dosyasını imzalama dosyasında ortak anahtarı yerleştirerek sağlar.

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>Açıklamalar

Benzer [/delaysign](delaysign-partially-sign-an-assembly.md) .winmd dosyasına uygulanan bağlayıcı seçeneği. Kullanım **/WINMDDELAYSIGN** .winmd dosyasında yalnızca ortak anahtar yerleştirmek istiyorsanız. Varsayılan olarak, bağlayıcı çalışır gibi **wınmddelaysıgn** belirtildi; diğer bir deyişle, bunun bir winmd dosyası oturum açmasını sağlamayan.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **Windows meta verileri** özellik sayfası.

1. İçinde **Windows meta verileri gecikmeli imza** aşağı açılan liste kutusunda, kullanmak istediğiniz seçeneği seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
