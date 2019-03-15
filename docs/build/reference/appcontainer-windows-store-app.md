---
title: / APPCONTAINER (UWP/Microsoft Store uygulaması)
ms.date: 11/04/2016
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
ms.openlocfilehash: f7ab8cf1ce034580953fdf1403264e8ef3d3ff09
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812414"
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

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler**, girin `/APPCONTAINER` veya `/APPCONTAINER:NO`.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
