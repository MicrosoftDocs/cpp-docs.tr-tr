---
title: Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: de5c9056402cb1db25240772eb3c592523daafae
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525330"
---
# <a name="provider-wizard-generated-files"></a>Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar

::: moniker range="vs-2019"

ATL OLE DB sağlayıcısı Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil.

::: moniker-end

::: moniker range="vs-2017"

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
