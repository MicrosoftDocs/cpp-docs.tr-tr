---
title: "Özellik eşlemeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 05bd576e6e55c94306a8dd648c57a4d606bed696
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="property-maps"></a>Özellik Eşlemeleri
Oturum, satır kümesi ve isteğe bağlı komut nesnesine ek olarak, her sağlayıcısı bir veya daha fazla özelliklerini destekler. Bu özellikler OLE DB Sağlayıcı Sihirbazı tarafından oluşturulan üstbilgi dosyalarında bulunan özellik eşlemeleri tanımlanır. Her üstbilgi dosyası nesne ya da bu dosyasında tanımlanan nesneleri için tanımlanan OLE DB özellik grubunun özellikleri için bir eşleme içerir. Veri kaynağı nesnesi içeren üstbilgi dosyası için özellik eşlemesi de içeren [veri kaynağı özellikleri](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx). Session.h içeren için özellik eşlemesi [oturum özellikleri](https://msdn.microsoft.com/en-us/library/ms714221.aspx). Satır kümesi ve komut nesneleri olarak adlandırılan bir tek üstbilgi dosyasında bulunan *projectname*RS.h. Bu özellikler, üyesi [satır kümesi özellikleri](https://msdn.microsoft.com/en-us/library/ms711252.aspx) grubu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)