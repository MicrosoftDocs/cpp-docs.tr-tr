---
title: Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: 3bc680e5999c077dda384823ec4f67d2456af284
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924320"
---
# <a name="provider-wizard-generated-files"></a>Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar

::: moniker range="msvc-160"

ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

**ATL OLE DB sağlayıcı Sihirbazı** aşağıdaki dosyaları oluşturur. Aşağıdaki konular *özel* kısa adı kullanır, ancak tam dosya adları sağlayıcıyı oluştururken yaptığınız seçime bağlıdır.

|Dosya adı|Açıklama|
|---------------|-----------------|
|*Özel* RS. cpp|Komut Yardımcısı `Execute` yöntemini ve sağlayıcı sütun haritasını içerir.|
|*Özel* DS. h|Veri kaynağı nesnesini uygular. Bu üstbilgi dosyası veri kaynağı özelliklerine ilişkin özellik eşlemesini içerir.|
|*Özel* RS. h|Komut ve satır kümesi nesnelerini uygular. Bu üstbilgi dosyası, satır kümesi ve komut özellikleri için özellik eşlemesini içerir.|
|*Özel* Sess. h|Oturum nesnesini uygular. Bu üstbilgi dosyası, oturum özellikleri için özellik eşlemesini içerir.|
|*Custom* . rgs|**OLE DB sağlayıcı Sihirbazı** tarafından oluşturulan kayıtlı nesneleri içerir.|

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)<br/>
