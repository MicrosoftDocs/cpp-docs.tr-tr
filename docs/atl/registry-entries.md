---
title: Kayıt defteri girdileri (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d74f458e28377dcc0bd7d6800cddc6e227c9f984
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751787"
---
# <a name="registry-entries"></a>Kayıt defteri girdileri

DCOM uygulaması, DCOM nesneleri bir veya daha fazla yapılandırma seçenekleri kayıt defteri merkezi bir konuma grup kimlikleri (uygulama) kavramını sundu. Bir AppID, adlandırılmış altında nesnenin CLSID değeri AppID değeriyle belirterek belirtin.

Varsayılan olarak, ATL tarafından oluşturulan bir hizmet kendi CLSID, AppID için GUID olarak kullanır. Altında `HKEY_CLASSES_ROOT\AppID`, DCOM özel girişleri belirtebilirsiniz. Başlangıçta, iki giriş mevcuttur:

- `LocalService`, hizmet adına eşit bir değere sahip. Bu değer mevcutsa yerine kullanılır `LocalServer32` CLSID altında anahtar.

- `ServiceParameters`, ona eşit bir değer ile `-Service`. Bu değer çalıştırıldığında hizmetine geçirilecek parametreleri belirtir. Bu parametre hizmetin geçirilen Not `ServiceMain` çalışmaz, `WinMain`.

Herhangi bir DCOM hizmet ayrıca altında başka bir anahtar oluşturmak gereken `HKEY_CLASSES_ROOT\AppID`. Bu anahtarı EXE adına eşit ve AppID girişleri işaret eden bir AppID değerini içeren bir çapraz başvuru işlevi görür.

## <a name="see-also"></a>Ayrıca Bkz.

[Hizmetler](../atl/atl-services.md)

