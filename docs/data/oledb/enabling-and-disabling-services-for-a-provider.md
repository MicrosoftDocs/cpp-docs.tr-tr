---
title: Sağlayıcı için Etkinleştirme ve Devre Dışı Bırakma Hizmetleri
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: 23579b9561356e95d315c0fbe47132208753afa8
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265132"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Sağlayıcı için Etkinleştirme ve Devre Dışı Bırakma Hizmetleri

OLE DB hizmetleri tek tek etkinleştirilebilir veya tek bir sağlayıcı erişen tüm uygulamalar için varsayılan olarak devre dışı. Bu, etkinleştirme veya devre dışı, hizmetler aşağıdaki tabloda gösterildiği gibi belirten bir DWORD değeri ile bir SAĞLAYICININ altında OLEDB_SERVICES kayıt defteri girdisi ekleyerek gerçekleştirilir.

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