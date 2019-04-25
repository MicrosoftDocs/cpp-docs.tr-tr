---
title: Kayıt defteri girdileri (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
ms.openlocfilehash: 7a89bc5d510d493f557b7ea74b8eabe5dfd87ac1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196761"
---
# <a name="registry-entries"></a>Kayıt defteri girdileri

DCOM uygulaması, DCOM nesneleri bir veya daha fazla yapılandırma seçenekleri kayıt defteri merkezi bir konuma grup kimlikleri (uygulama) kavramını sundu. Bir AppID, adlandırılmış altında nesnenin CLSID değeri AppID değeriyle belirterek belirtin.

Varsayılan olarak, ATL tarafından oluşturulan bir hizmet kendi CLSID, AppID için GUID olarak kullanır. Altında `HKEY_CLASSES_ROOT\AppID`, DCOM özel girişleri belirtebilirsiniz. Başlangıçta, iki giriş mevcuttur:

- `LocalService`, hizmet adına eşit bir değere sahip. Bu değer mevcutsa yerine kullanılır `LocalServer32` CLSID altında anahtar.

- `ServiceParameters`, ona eşit bir değer ile `-Service`. Bu değer çalıştırıldığında hizmetine geçirilecek parametreleri belirtir. Bu parametre hizmetin geçirilen Not `ServiceMain` çalışmaz, `WinMain`.

Herhangi bir DCOM hizmet ayrıca altında başka bir anahtar oluşturmak gereken `HKEY_CLASSES_ROOT\AppID`. Bu anahtarı EXE adına eşit ve AppID girişleri işaret eden bir AppID değerini içeren bir çapraz başvuru işlevi görür.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)
