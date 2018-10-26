---
title: Sağlayıcı Sihirbazı tarafından üretilen dosyalar | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
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
ms.openlocfilehash: a9bc7c85dccdfe095412450d5020fc8a6b42d516
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076977"
---
# <a name="provider-wizard-generated-files"></a>Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar

ATL OLE DB sağlayıcısı Sihirbazı, aşağıdaki dosyaları oluşturur. Kısa ad aşağıdaki konuları kullanın *özel*, ancak tam dosya adlarını sağlayıcısı oluşturulurken yaptığınız seçimi bağlıdır.

|Dosya adı|Açıklama|
|---------------|-----------------|
|*Özel*RS.cpp|Komut Yardımcısı içeren `Execute` yöntemi ve sağlayıcı sütun eşlemesi.|
|*Özel*DS.h|Veri kaynağı nesnesinin uygular. Bu başlık dosyasının özellik eşlemesi için veri kaynağı özellikleri içerir.|
|*Özel*RS.h|Komut ve rowset nesneleri uygular. Bu başlık dosyasının satır kümesi ve komut özellikleri için özellik eşlemesi içerir.|
|*Özel*Sess.h|Oturum nesnesi uygular. Bu başlık dosyasının özellik eşlemesi için oturum özellikleri içerir.|
|*Özel*.rgs|OLE DB sağlayıcısı Sihirbazı tarafından oluşturulan kayıtlı nesneler içerir.|

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)