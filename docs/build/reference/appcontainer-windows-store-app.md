---
title: / APPCONTAINER (UWP/Microsoft Store uygulaması) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d52148f14c21773a6fe93c3909c91f80c3c3650
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726576"
---
# <a name="appcontainer-microsoft-store-app"></a>/ APPCONTAINER (Microsoft Store uygulaması)

Bağlayıcı, bir uygulama kapsayıcısında çalıştırılması gereken bir yürütülebilir görüntü oluşturup oluşturmayacağını belirtir.

## <a name="syntax"></a>Sözdizimi

```
/APPCONTAINER[:NO]
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak/appcontaıner kapalıdır.

Bu seçenek, uygulamanın appcontainer işlem yalıtımı ortamında çalıştırılması gereken olup olmadığını belirtmek için bir yürütülebilir dosya değiştirir. Ortamında çalıştırılması gereken bir uygulama için/appcontaıner belirtin — örneğin, Evrensel Windows Platformu (UWP) veya Windows Phone 8.x uygulaması. (Bir şablondan bir evrensel Windows uygulaması oluştururken seçeneğini otomatik olarak Visual Studio'da ayarlanır.) Bir masaüstü uygulaması için /APPCONTAINER:NO belirtin veya seçeneği atlayın.

/ Appcontaıner seçeneği, Windows 8'de sunulmuştur.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneğini ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler**, girin `/APPCONTAINER` veya `/APPCONTAINER:NO`.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)