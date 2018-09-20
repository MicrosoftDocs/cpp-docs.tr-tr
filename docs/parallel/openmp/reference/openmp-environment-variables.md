---
title: OpenMP ortam değişkenleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b61535fd07066c4a1ee24658fdfe81047efc90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446575"
---
# <a name="openmp-environment-variables"></a>OpenMP Ortam Değişkenleri

OpenMP API çağrısında kullanılan ortam değişkenlerini bağlantılar sağlar.

Standart OpenMP Visual C++ uygulaması, aşağıdaki ortam değişkenlerini içerir. Bu ortam değişkenleri, program başlangıcında okunduğu ve değerlerine yapılan değişiklikler çalışma zamanında yok sayıldı (örnek olarak, [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

|ortam değişkeni|Açıklama|
|--------------------------|-----------------|
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Çalışma zamanı OpenMP bir paralel bölgenin içinde iş parçacığı sayısını ayarlayıp ayarlayamayacağını belirler.|
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|İç içe geçmiş paralellik etkin veya ile devre dışı sürece iç içe geçmiş paralellik, etkin olup olmadığını belirten `omp_set_nested`.|
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|İş parçacığı sayısı tarafından geçersiz kılınmadığı sürece paralel bölgenin içinde ayarlar [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) veya [num_threads](../../../parallel/openmp/reference/num-threads.md).|
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Davranışını değiştiren [zamanlama](../../../parallel/openmp/reference/schedule.md) yan tümcesi olduğunda `schedule(runtime)` belirtilen bir `for` veya `parallel for` yönergesi.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık Başvurusu](../../../parallel/openmp/reference/openmp-library-reference.md)