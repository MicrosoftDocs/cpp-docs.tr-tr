---
title: Etkinleştirme ve devre dışı bırakma sağlayıcı için Hizmetleri | Microsoft Docs
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
ms.openlocfilehash: ef36e35234aa4878e30e70748a5b2ba2975c38dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099738"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Sağlayıcı için Etkinleştirme ve Devre Dışı Bırakma Hizmetleri
Tek tek OLE DB hizmetleri, etkin veya tek sağlayıcıya erişen tüm uygulamalar için varsayılan olarak devre dışı. Bu ekleyerek yapılır bir **OLEDB_SERVICES** sağlayıcı altında kayıt defteri girdisi ile CLSID, kullanıcının bir `DWORD` için hizmetleri etkinleştirmek veya devre dışı bırakmak, aşağıdaki tabloda gösterildiği gibi belirten değer.  
  
|Varsayılan hizmetler etkin|Anahtar değeri|  
|------------------------------|-------------------|  
|Tüm hizmetler (varsayılan)|0xFFFFFFFF|  
|Hariç tüm ve AutoEnlistment|0xFFFFFFFE|  
|Tüm istemci imleci hariç|0xfffffffb|  
|Tüm hariç, AutoEnlistment ve istemci imleci|0xfffffff0|  
|Hizmet yok|0x00000000|  
|Hiçbir toplama, tüm hizmetleri devre dışı|\<Eksik anahtar >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma](../../data/oledb/enabling-and-disabling-ole-db-services.md)