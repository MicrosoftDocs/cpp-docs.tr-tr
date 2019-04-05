---
title: Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar
ms.date: 10/18/2018
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: a9a706463326249135a55bc907cb8a664a3ca808
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037097"
---
# <a name="provider-wizard-generated-files"></a>Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar

**ATL OLE DB sağlayıcısı Sihirbazı** aşağıdaki dosyaları oluşturur. Kısa ad aşağıdaki konuları kullanın *özel*, ancak tam dosya adlarını sağlayıcısı oluşturulurken yaptığınız seçimi bağlıdır.

|Dosya adı|Açıklama|
|---------------|-----------------|
|*Özel*RS.cpp|Komut Yardımcısı içeren `Execute` yöntemi ve sağlayıcı sütun eşlemesi.|
|*Özel*DS.h|Veri kaynağı nesnesinin uygular. Bu başlık dosyasının özellik eşlemesi için veri kaynağı özellikleri içerir.|
|*Özel*RS.h|Komut ve rowset nesneleri uygular. Bu başlık dosyasının satır kümesi ve komut özellikleri için özellik eşlemesi içerir.|
|*Özel*Sess.h|Oturum nesnesi uygular. Bu başlık dosyasının özellik eşlemesi için oturum özellikleri içerir.|
|*Özel*.rgs|Tarafından oluşturulan kayıtlı nesneler içeren **OLE DB sağlayıcısı Sihirbazı**.|

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)<br/>
