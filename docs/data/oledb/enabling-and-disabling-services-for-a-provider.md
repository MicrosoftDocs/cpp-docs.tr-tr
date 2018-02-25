---
title: "Etkinleştirme ve devre dışı bırakma sağlayıcı için Hizmetleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 60e54d9d02cc819c9eaf7674257d846c537da615
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Sağlayıcı için Etkinleştirme ve Devre Dışı Bırakma Hizmetleri
Tek tek OLE DB hizmetleri, etkin veya tek sağlayıcıya erişen tüm uygulamalar için varsayılan olarak devre dışı. Bu ekleyerek yapılır bir **OLEDB_SERVICES** sağlayıcı altında kayıt defteri girdisi ile CLSID, kullanıcının bir `DWORD` için hizmetleri etkinleştirmek veya devre dışı bırakmak, aşağıdaki tabloda gösterildiği gibi belirten değer.  
  
|Varsayılan hizmetler etkin|Anahtar değeri|  
|------------------------------|-------------------|  
|Tüm hizmetler (varsayılan)|0xffffffff|  
|Hariç tüm ve AutoEnlistment|0xfffffffe|  
|Tüm istemci imleci hariç|0xfffffffb|  
|Tüm hariç, AutoEnlistment ve istemci imleci|0xfffffff0|  
|Hizmet yok|0x00000000|  
|Hiçbir toplama, tüm hizmetleri devre dışı|\<Eksik anahtar >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma](../../data/oledb/enabling-and-disabling-ole-db-services.md)