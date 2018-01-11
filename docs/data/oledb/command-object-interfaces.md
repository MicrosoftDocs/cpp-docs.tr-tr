---
title: Komut nesnesi arabirimleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3d83f0a14562985386f0f1f75cfcd99518fea6f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="command-object-interfaces"></a>Komut Nesnesi Arabirimleri
Komut nesnesi kullanır `IAccessor` parametre bağlamaları belirtmek için arabirim. Tüketici çağrıları `IAccessor::CreateAccessor`, bir dizi geçirme `DBBINDING` yapıları. `DBBINDING`Sütun bağlamaları (örneğin, türü ve uzunluğu) hakkında bilgi içerir. Sağlayıcı yapıları alır ve verileri nasıl aktarılması gerektiğini ve dönüştürmenin gerekli olup belirler.  
  
 `ICommandText` Arabirimi metin komutu belirtmek için bir yol sağlar. `ICommandProperties` Arabirimi tüm komut özellikleri işler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)