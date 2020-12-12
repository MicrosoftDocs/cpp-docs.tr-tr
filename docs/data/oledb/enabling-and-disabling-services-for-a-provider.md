---
description: 'Hakkında daha fazla bilgi edinin: bir sağlayıcı için hizmetleri etkinleştirme ve devre dışı bırakma'
title: Sağlayıcı için Etkinleştirme ve Devre Dışı Bırakma Hizmetleri
ms.date: 07/30/2019
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: ead2ce9b8f1e678af00bcc03140c2868986a1564
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287547"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Sağlayıcı için Etkinleştirme ve Devre Dışı Bırakma Hizmetleri

Tek bir sağlayıcıya erişen tüm uygulamalar için bireysel OLE DB hizmetleri varsayılan olarak etkinleştirilebilir veya devre dışı bırakılabilir. Bu işlem, aşağıdaki tabloda gösterildiği gibi, etkinleştirilecek veya devre dışı bırakılacak Hizmetleri belirten bir DWORD değeriyle sağlayıcının CLSID altına bir OLEDB_SERVICES kayıt defteri girişi eklenerek yapılır.

|Varsayılan hizmetler etkin|DWORD değeri|
|------------------------------|-------------------|
|İstemci imleci ve havuzu hariç tüm hizmetler|0xfffffffa|
|İstemci İmleci hariç tüm hizmetler|0xfffffffb|
|Havuz ve otomatik kayıt hariç tüm hizmetler|0xfffffffc|
|Havuz hariç tüm hizmetler|0xfffffffe|
|Tüm hizmetler (varsayılan)|ffffffff|
|Hizmet yok|0x00000000|
|Toplama yok, tüm hizmetler devre dışı|OLEDB_Services kayıt defteri girdisi yok|

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB hizmetlerini etkinleştirme ve devre dışı bırakma](../../data/oledb/enabling-and-disabling-ole-db-services.md)
