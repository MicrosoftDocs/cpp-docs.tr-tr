---
title: Kayıt defteri girdileri (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
ms.openlocfilehash: b61aae9ba9316dded1dcb11353e52eb2fffd49a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472884"
---
# <a name="registry-entries"></a>Kayıt defteri girdileri

DCOM uygulaması, DCOM nesneleri bir veya daha fazla yapılandırma seçenekleri kayıt defteri merkezi bir konuma grup kimlikleri (uygulama) kavramını sundu. Bir AppID, adlandırılmış altında nesnenin CLSID değeri AppID değeriyle belirterek belirtin.

Varsayılan olarak, ATL tarafından oluşturulan bir hizmet kendi CLSID, AppID için GUID olarak kullanır. Altında `HKEY_CLASSES_ROOT\AppID`, DCOM özel girişleri belirtebilirsiniz. Başlangıçta, iki giriş mevcuttur:

- `LocalService`, hizmet adına eşit bir değere sahip. Bu değer mevcutsa yerine kullanılır `LocalServer32` CLSID altında anahtar.

- `ServiceParameters`, ona eşit bir değer ile `-Service`. Bu değer çalıştırıldığında hizmetine geçirilecek parametreleri belirtir. Bu parametre hizmetin geçirilen Not `ServiceMain` çalışmaz, `WinMain`.

Herhangi bir DCOM hizmet ayrıca altında başka bir anahtar oluşturmak gereken `HKEY_CLASSES_ROOT\AppID`. Bu anahtarı EXE adına eşit ve AppID girişleri işaret eden bir AppID değerini içeren bir çapraz başvuru işlevi görür.

## <a name="see-also"></a>Ayrıca Bkz.

[Hizmetler](../atl/atl-services.md)

