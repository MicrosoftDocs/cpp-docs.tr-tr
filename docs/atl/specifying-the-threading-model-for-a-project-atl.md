---
description: 'Hakkında daha fazla bilgi edinin: bir proje için Iş parçacıklı model belirtme (ATL)'
title: Proje İçin İş Parçacıklı Model Belirtme (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
ms.openlocfilehash: 81bf8413a2118797ec0e0c177a06468b8e3c7ba0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138482"
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>Proje İçin İş Parçacıklı Model Belirtme (ATL)

Aşağıdaki makrolar, ATL projesinin iş parçacığı modelini belirtmek için kullanılabilir:

|Makroya|Kullanma yönergeleri|
|-----------|--------------------------|
|_ATL_SINGLE_THREADED|Tüm nesnelerinizin tek iş parçacığı modelini kullanıp kullan, tanımlayın.|
|_ATL_APARTMENT_THREADED|Nesnelerinizin bir veya daha fazla apartman iş parçacığı kullanıp kullanmıyorsa tanımlayın.|
|_ATL_FREE_THREADED|Nesnelerinizin bir veya daha fazla serbest iş parçacığı kullanıp kullanmıyorsa tanımlayın. Mevcut kod, [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded)eşdeğer makro başvuruları içerebilir.|

Projeniz için bu makroların hiçbirini tanımlamadıysanız _ATL_FREE_THREADED yürürlüğe girer.

Makrolar, çalışma zamanı performansını aşağıdaki şekilde etkiler:

- Projenizdeki nesnelere karşılık gelen makroyu belirtmek, çalışma zamanı performansını iyileştirebilir.

- Daha yüksek bir makro düzeyi belirtme Örneğin, tüm nesneleriniz tek iş parçacıklı olduğunda _ATL_APARTMENT_THREADED belirtirseniz, çalışma zamanı performansını biraz düşürür.

- Örneğin, bir veya daha fazla nesneniz apartman iş parçacığı veya serbest iş parçacığı kullanırken _ATL_SINGLE_THREADED belirtirseniz, çalışma zamanında uygulamanızın başarısız olmasına neden olabilir.

ATL nesnesi için kullanılabilen iş parçacığı modellerinin bir açıklaması için bkz. [Seçenekler, atl basit nesne Sihirbazı](../atl/reference/options-atl-simple-object-wizard.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)
