---
title: "Basit salt okunur sağlayıcı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 67ffacffde8dc13e49a09358efcafefd751619ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-simple-read-only-provider"></a>Basit bir Salt Okunur Sağlayıcı Oluşturma
ATL Proje Sihirbazı ve ATL OLE DB Sağlayıcı Sihirbazı'nı kullanarak bir OLE DB sağlayıcısı oluşturduğunuzda, desteklemek istediğiniz diğer işlevleri ekleyebilirsiniz. Ne tür veriler, tüketiciye ve hangi koşullarda göndereceği inceleyerek sağlayıcınızı tasarlamaya başlayın. Komutları, işlemleri ve diğer isteğe bağlı nesneleri destek gerekip gerekmediğini belirlemek özellikle önemlidir. Önden iyi bir tasarım, uygulama ve sınamayı hızlandırır.  
  
 Örneğin, iki parça halinde sunulur:  
  
-   İlk bölümü gösterir nasıl [basit bir salt okunur sağlayıcı oluşturma](../../data/oledb/implementing-the-simple-read-only-provider.md) dizeleri çifti okur.  
  
-   İkinci bölümü gösterir nasıl [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md) ekleyerek `IRowsetLocate` arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)