---
title: Etkinleştirme ve devre dışı bırakma Hizmetleri sağlayıcısının | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5db612c836e4b902e7cad83017661246f4b649e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079394"
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