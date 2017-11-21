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
ms.openlocfilehash: 734018229eff0db3a1ed1a779be39e59b75447f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="command-object-interfaces"></a>Komut Nesnesi Arabirimleri
Komut nesnesi kullanır `IAccessor` parametre bağlamaları belirtmek için arabirim. Tüketici çağrıları `IAccessor::CreateAccessor`, bir dizi geçirme `DBBINDING` yapıları. `DBBINDING`Sütun bağlamaları (örneğin, türü ve uzunluğu) hakkında bilgi içerir. Sağlayıcı yapıları alır ve verileri nasıl aktarılması gerektiğini ve dönüştürmenin gerekli olup belirler.  
  
 `ICommandText` Arabirimi metin komutu belirtmek için bir yol sağlar. `ICommandProperties` Arabirimi tüm komut özellikleri işler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)