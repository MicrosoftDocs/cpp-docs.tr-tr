---
title: Sağlayıcı Sihirbazı tarafından üretilen dosyalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 26e20e0417e2253158930a8d3d055171fe767001
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108410"
---
# <a name="provider-wizard-generated-files"></a>Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar

ATL OLE DB sağlayıcısı Sihirbazı, aşağıdaki dosyaları oluşturur. Kısa ad "MyProvider" aşağıdaki konuları kullanın, ancak tam dosya adlarını sağlayıcısı oluşturulurken yaptığınız seçiminize bağlıdır.  
  
|Dosya adı|Açıklama|  
|---------------|-----------------|  
|MyProviderRS.cpp|Komut Yardımcısı içeren `Execute` yöntemi ve sağlayıcı sütun eşlemesi.|  
|MyProviderDS.h üzerinde|Veri kaynağı nesnesinin uygular. Bu başlık dosyasının özellik eşlemesi için veri kaynağı özellikleri içerir.|  
|MyProviderRS.h|Komut ve rowset nesneleri uygular. Bu başlık dosyasının satır kümesi ve komut özellikleri için özellik eşlemesi içerir.|  
|MyProviderSess.h|Oturum nesnesi uygular. Bu başlık dosyasının özellik eşlemesi için oturum özellikleri içerir.|  
|MyProvider.rgs|OLE DB sağlayıcısı Sihirbazı tarafından oluşturulan kayıtlı nesneler içerir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)