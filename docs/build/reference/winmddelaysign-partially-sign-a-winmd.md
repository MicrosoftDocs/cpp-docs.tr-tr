---
description: Daha fazla bilgi edinin:/WINMDDELAYSIGN (bir WinMD 'yi kısmen Imzala)
title: /WINMDDELAYSIGN (winmd Dosyasını Kısmen İmzalayın)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 801b172f52a9beb9d09617644b3096e460359724
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259064"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (winmd Dosyasını Kısmen İmzalayın)

Ortak anahtarı dosyaya yerleştirerek bir Windows Çalışma Zamanı meta veri (. winmd) dosyasının kısmi imzalanmasını mümkün.

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>Açıklamalar

. Winmd dosyasına uygulanan [/delaysign](delaysign-partially-sign-an-assembly.md) bağlayıcı seçeneğine benzer. . Winmd dosyasına yalnızca ortak anahtar koymak istiyorsanız **/Winmddelaysign** kullanın. Varsayılan olarak, bağlayıcı **/Winmddelaysign: No** belirtilmişse gibi davranır; Yani, winmd dosyasını imzalamaz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörünü seçin.

1. **Windows meta verileri** özellik sayfasını seçin.

1. **Windows meta verileri gecikmesi oturum açma** aşağı açılan liste kutusunda istediğiniz seçeneği belirleyin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
