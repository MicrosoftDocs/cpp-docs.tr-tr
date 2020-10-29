---
title: Seçenekler, ATL Özellik sayfası Sihirbazı
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: 74cf72feedd8dc8e1186d54a8abe840195964620
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923664"
---
# <a name="options-atl-property-page-wizard"></a>Seçenekler, ATL Özellik sayfası Sihirbazı

::: moniker range="msvc-160"

ATL Özellik sayfası Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

Oluşturmakta olduğunuz özellik sayfasının iş parçacığı modelini ve toplama düzeyini tanımlamak için sihirbazın bu sayfasını kullanın.

- **İş parçacığı modeli**

   Özellik sayfası tarafından kullanılan iş parçacığı modelini belirtir.

   Daha fazla bilgi için bkz. [projenin Iş parçacığı modelini belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) .

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Tek**|Özellik sayfası yalnızca birincil COM iş parçacığında çalışır.|
   |**Yapı**|Özellik sayfası herhangi bir tek iş parçacığı grubu içinde oluşturulabilir. Varsayılan.|

- **Toplama**

   Oluşturmakta olduğunuz özellik sayfası için toplama desteği ekler. Daha fazla bilgi için bkz. [toplama](../../atl/aggregation.md) .

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Evet**|Toplanabilecek bir özellik sayfası oluşturun.|
   |**Hayır**|Toplanmayan bir özellik sayfası oluşturun.|
   |**Yalnızca**|Yalnızca toplama yoluyla örneklenebilir bir özellik sayfası oluşturun.|

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL Özellik Sayfası Sihirbazı](../../atl/reference/atl-property-page-wizard.md)<br/>
[Dizeler, ATL Özellik sayfası Sihirbazı](../../atl/reference/strings-atl-property-page-wizard.md)
