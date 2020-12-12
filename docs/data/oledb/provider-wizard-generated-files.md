---
description: 'Daha fazla bilgi edinin: sağlayıcı Wizard-Generated dosyaları'
title: Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: 95c9641f10acef4a55b8de15752eb125e75d874a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316901"
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
|*Custom*. rgs|**OLE DB sağlayıcı Sihirbazı** tarafından oluşturulan kayıtlı nesneleri içerir.|

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcısı oluşturma](../../data/oledb/creating-an-ole-db-provider.md)<br/>
