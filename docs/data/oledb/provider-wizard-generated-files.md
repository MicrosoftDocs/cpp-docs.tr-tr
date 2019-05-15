---
title: Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: 0638680482546f56f26b70660ab43bd9848438a3
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707482"
---
# <a name="provider-wizard-generated-files"></a>Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar

::: moniker range="vs-2019"

ATL OLE DB sağlayıcısı Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil.

::: moniker-end

::: moniker range="<=vs-2017"

**ATL OLE DB sağlayıcısı Sihirbazı** aşağıdaki dosyaları oluşturur. Kısa ad aşağıdaki konuları kullanın *özel*, ancak tam dosya adlarını sağlayıcısı oluşturulurken yaptığınız seçimi bağlıdır.

|Dosya adı|Açıklama|
|---------------|-----------------|
|*Özel*RS.cpp|Komut Yardımcısı içeren `Execute` yöntemi ve sağlayıcı sütun eşlemesi.|
|*Özel*DS.h|Veri kaynağı nesnesinin uygular. Bu başlık dosyasının özellik eşlemesi için veri kaynağı özellikleri içerir.|
|*Özel*RS.h|Komut ve rowset nesneleri uygular. Bu başlık dosyasının satır kümesi ve komut özellikleri için özellik eşlemesi içerir.|
|*Özel*Sess.h|Oturum nesnesi uygular. Bu başlık dosyasının özellik eşlemesi için oturum özellikleri içerir.|
|*Özel*.rgs|Tarafından oluşturulan kayıtlı nesneler içeren **OLE DB sağlayıcısı Sihirbazı**.|

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)<br/>
