---
title: 3. Çalışma zamanı kitaplık işlevleri
ms.date: 11/04/2016
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
ms.openlocfilehash: e1d8d498be7f58bcf510025c67c539127f450824
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484103"
---
# <a name="3-run-time-library-functions"></a>3. Çalışma zamanı kitaplık işlevleri

Bu bölümde OpenMP C ve C++ çalışma zamanı kitaplık işlevleri açıklanmaktadır. Üst bilgi  **\<omp.h >** iki tür, denetlemek ve Paralel yürütme ortamı sorgu ve veri erişimi eşitlemek için kullanılan işlevleri kilitlemek için kullanılan çeşitli işlevleri bildirir.

Türü **omp_lock_t** bir nesne türü bir kilit kullanılabilir gösterebilen ya da bir iş parçacığı bir kilit sahibi. Bu kilitleri olarak ifade edilir *basit kilit*.

Türü **omp_nest_lock_t** ya da, gösterebilen bir nesne türü bir kilit kullanılabilir veya her iki iş parçacığı kimliğine sahip olan kilidi ve *sayısı iç içe* (aşağıda açıklanmıştır). Bu kilitleri olarak ifade edilir *nestable kilit*.

Kitaplık işlevleri, "C" bağlaması olan dış işlevlerdir.

Açıklamalar bu bölümdeki aşağıdaki konularla ayrılır:

- Yürütme Ortamı işlevleri (bkz [bölümü 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) sayfasında 35).

- Kilit işlevleri (bkz [bölümü 3.2](../../parallel/openmp/3-2-lock-functions.md) sayfasında 41).