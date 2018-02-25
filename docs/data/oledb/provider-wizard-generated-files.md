---
title: "Sağlayıcı Sihirbazı tarafından üretilen dosyalar | Microsoft Docs"
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
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9cfcce4242cf985b8ffa50b9df234d609cfe7f3f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="provider-wizard-generated-files"></a>Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar
ATL OLE DB Sağlayıcı Sihirbazı aşağıdaki dosyaları oluşturur. Kısa ad "MyProvider" aşağıdaki konuları kullanın, ancak tam dosya isimleri sağlayıcıyı oluştururken yapılan seçiminize bağlıdır.  
  
|Dosya adı|Açıklama|  
|---------------|-----------------|  
|MyProviderRS.cpp|Komut Yardımcısı içeren `Execute` yöntemi ve sağlayıcı sütun eşlemesi.|  
|MyProviderDS.h|Veri kaynağı nesnesi uygular. Bu başlık dosyası veri kaynağı özellikleri için özellik eşlemesi içerir.|  
|MyProviderRS.h|Komut ve satır kümesi nesneleri uygular. Bu başlık dosyası satır kümesi ve komut özellikleri için özellik eşlemesi içerir.|  
|MyProviderSess.h|Oturum nesnesi uygular. Bu başlık dosyası oturum özellikleri için özellik eşlemesi içerir.|  
|MyProvider.rgs|OLE DB Sağlayıcı Sihirbazı tarafından oluşturulan kayıtlı nesneleri içerir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)