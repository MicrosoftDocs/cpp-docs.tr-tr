---
description: Şu konuda daha fazla bilgi edinin:/APPCONTAINER (Microsoft Store uygulaması)
title: /APPCONTAINER (UWP/Microsoft Store uygulaması)
ms.date: 11/04/2016
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
ms.openlocfilehash: 4cb78c85aa59ebd7fc0eb82af9497606bc3c431c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179583"
---
# <a name="appcontainer-microsoft-store-app"></a>/APPCONTAINER (Microsoft Store uygulaması)

Bağlayıcının bir uygulama kapsayıcısında çalıştırılması gereken bir yürütülebilir görüntü oluşturup oluşturmadığını belirtir.

## <a name="syntax"></a>Syntax

```
/APPCONTAINER[:NO]
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak,/APPCONTAINER kapalıdır.

Bu seçenek, uygulamanın AppContainer işlem yalıtım ortamında çalıştırılması gerekip gerekmediğini belirtmek için bir yürütülebilir dosyayı değiştirir. APPCONTAINER ortamında çalışması gereken bir uygulama için/APPCONTAINER belirtin — örneğin, bir Evrensel Windows Platformu (UWP) veya Windows Phone 8. x uygulaması. (Bir şablondan bir Evrensel Windows uygulaması oluşturduğunuzda, bu seçenek Visual Studio 'da otomatik olarak ayarlanır.) Bir masaüstü uygulaması için/APPCONTAINER: NO belirtin veya seçeneği atlayın.

/APPCONTAINER seçeneği Windows 8 ' de tanıtılmıştır.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünü genişletin.

1. **Bağlayıcı** düğümünü genişletin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler**' de, `/APPCONTAINER` veya girin `/APPCONTAINER:NO` .

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
