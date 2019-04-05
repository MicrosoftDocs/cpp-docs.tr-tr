---
title: Sağlayıcı için Etkinleştirme ve Devre Dışı Bırakma Hizmetleri
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: d91f08accf1a8be69f63d6bbcaa4c620d68c1077
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033037"
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

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma](../../data/oledb/enabling-and-disabling-ole-db-services.md)