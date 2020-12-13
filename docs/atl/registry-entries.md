---
description: 'Daha fazla bilgi için: kayıt defteri girişleri'
title: Kayıt defteri girdileri (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
ms.openlocfilehash: c89c8f64a91c09f16333c3381a33d792332543d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138586"
---
# <a name="registry-entries"></a>Kayıt defteri girdileri

DCOM, bir veya daha fazla DCOM nesnesi için yapılandırma seçeneklerini kayıt defterinde merkezi bir konuma grup olarak belirleyen uygulama kimlikleri (Appıds) kavramını sunmuştur. Bir AppID 'yi, nesne CLSID 'SI altındaki değer adlı uygulama adı içinde değerini belirterek belirtirsiniz.

Varsayılan olarak, ATL tarafından oluşturulan bir hizmet onun CLSID 'sini uygulama kimliği olarak kullanır. Altında `HKEY_CLASSES_ROOT\AppID` , DCOM 'a özgü girdileri belirtebilirsiniz. Başlangıçta, iki giriş vardır:

- `LocalService`, hizmetin adına eşit bir değere sahip. Bu değer varsa, `LocalServer32` CLSID altındaki anahtar yerine kullanılır.

- `ServiceParameters`, değerine eşit değeri olan `-Service` . Bu değer, başlatıldığında hizmete geçirilecek parametreleri belirtir. Bu parametrelerin hizmetin işlevine geçirildiğine unutmayın `ServiceMain` `WinMain` .

Tüm DCOM hizmetleri de altında başka bir anahtar oluşturması gerekir `HKEY_CLASSES_ROOT\AppID` . Bu anahtar, EXE adına eşittir ve AppID girişlerine geri işaret eden bir AppID değeri içerdiğinden çapraz başvuru işlevi görür.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)
