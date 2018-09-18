---
title: Basit bir salt okunur sağlayıcı oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9f951fba45b23b7e4dde92fc11f2faabb53bd43d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101572"
---
# <a name="creating-a-simple-read-only-provider"></a>Basit bir Salt Okunur Sağlayıcı Oluşturma

ATL OLE DB sağlayıcısı Sihirbazı'nı ve ATL projesi Sihirbazı'nı kullanarak bir OLE DB sağlayıcısı oluştururken, desteklemek istediğiniz diğer işlevleri ekleyebilirsiniz. Ne tür veriler, tüketici ve hangi koşullar altında göndereceği inceleyerek sağlayıcınız tasarlamaya başlayabilir. Komutlar, işlemleri ve diğer isteğe bağlı nesneler destek gerekip gerekmediğini belirlemek özellikle önemlidir. Önden iyi bir tasarım, uygulama ve test hızlandırır.  
  
Örneğin, iki parça halinde sunulur:  
  
- İlk bölümü gösterir nasıl [basit bir salt okunur sağlayıcı oluşturma](../../data/oledb/implementing-the-simple-read-only-provider.md) , dizelerden oluşan bir çift okur.  
  
- İkinci bölümü gösterir nasıl [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md) ekleyerek `IRowsetLocate` arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)