---
title: Sağlayıcı için Etkinleştirme ve Devre Dışı Bırakma Hizmetleri
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: ca621b005dd0bad60c70298e4d49abce6fb8d1d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665458"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Sağlayıcı için Etkinleştirme ve Devre Dışı Bırakma Hizmetleri

OLE DB hizmetleri tek tek etkinleştirilebilir veya tek bir sağlayıcı erişen tüm uygulamalar için varsayılan olarak devre dışı. Bu SAĞLAYICININ altında bir OLEDB_SERVICES kayıt defteri girdisi ekleyerek yapılır bir `DWORD` etkinleştirme veya devre dışı, hizmetler aşağıdaki tabloda gösterildiği gibi belirten değer.

|Varsayılan hizmetler etkin|Anahtar değeri|
|------------------------------|-------------------|
|Tüm hizmetler (varsayılan)|0xFFFFFFFF|
|Havuzu hariç ve AutoEnlistment|0xFFFFFFFE|
|Tüm istemci imleci hariç|0xfffffffb|
|Tümünü hariç, AutoEnlistment ve istemci imleci|0xfffffff0|
|Hizmet yok|0x00000000|
|Toplama yoktur, tüm hizmetleri devre dışı bırakıldı|\<Eksik anahtar >|

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma](../../data/oledb/enabling-and-disabling-ole-db-services.md)