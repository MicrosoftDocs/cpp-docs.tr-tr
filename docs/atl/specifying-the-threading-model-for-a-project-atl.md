---
title: Proje İçin İş Parçacıklı Model Belirtme (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
ms.openlocfilehash: 69c1c80bba0b09ce69e0b9b9b27296ef2508e60b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275223"
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>Proje İçin İş Parçacıklı Model Belirtme (ATL)

Aşağıdaki makroları ATL projesinde iş parçacığı modeli belirtmek kullanılabilir:

|Makrosu|Kullanma yönergeleri|
|-----------|--------------------------|
|_ATL_SINGLE_THREADED|Tek iş parçacıklı model nesnelerinizi tüm kullandıysanız tanımlayın.|
|_ATL_APARTMENT_THREADED|Bir veya daha fazla nesnelerinizi iş parçacığı grubu kullanıyorsanız tanımlayın.|
|_ATL_FREE_THREADED|Bir veya daha fazla nesnelerinizi ücretsiz veya nötr iş parçacığı kullanırsanız tanımlayın. Var olan kod, eşdeğer makrosu başvuruları içerebilir [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded).|

Projeniz için bu makrolar birini tanımlamazsanız _ATL_FREE_THREADED uygulanmaz.

Makrolar gibi çalışma zamanı performansını etkiler:

- Projenizdeki nesnelere karşılık gelen makro belirtme, çalışma zamanı performansını artırabilir.

- Makrosu, nesnelerinizin tüm iş parçacıklı, tek olduğunda _ATL_APARTMENT_THREADED belirtirseniz, örneğin daha yüksek bir düzeyde belirtme biraz çalışma zamanı performansını bozar.

- _Atl_sıngle_threaded biri belirtin veya nesnelerinizin daha fazla iş parçacığı grubu veya serbest iş parçacığı oluşturma, kullanırsanız, makro, örneğin, daha düşük bir düzeyde belirtme, uygulamanızın çalışma zamanında başarısız olmasına neden olabilir.

Bkz: [ATL Basit Nesne Sihirbazı, seçenekleri](../atl/reference/options-atl-simple-object-wizard.md) iş parçacığı için bir açıklama modeller bir ATL nesnesi için kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)
