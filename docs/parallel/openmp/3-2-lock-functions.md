---
title: 3.2 Kilit İşlevleri
ms.date: 11/04/2016
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
ms.openlocfilehash: c189ba5b1f0bb365b387b4b4b887cfdb74d1bf2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573075"
---
# <a name="32-lock-functions"></a>3.2 Kilit İşlevleri

Bu bölümde açıklanan işlevler, eşitleme için kullanılan kilit işleyin.

Aşağıdaki işlevler için kilit değişken türüne sahip olmalıdır **omp_lock_t**. Bu değişken, yalnızca bu işlevleri aracılığıyla erişilmelidir. Tüm kilit işlevleri bir işaretçiye sahip bir bağımsız değişken gerektirir **omp_lock_t** türü.

- `omp_init_lock` İşlevi basit kilit başlatır.

- `omp_destroy_lock` İşlevi basit kilit kaldırır.

- `omp_set_lock` İşlevi, bir basit kilit kullanılabilir oluncaya kadar bekler.

- `omp_unset_lock` İşlevi basit bir kilidi serbest bırakır.

- `omp_test_lock` İşlevi, bir basit kilit test.

Aşağıdaki işlevler için kilit değişken türüne sahip olmalıdır **omp_nest_lock_t**.  Bu değişken, yalnızca bu işlevleri aracılığıyla erişilmelidir. Tüm nestable kilit işlevleri bir işaretçiye sahip bir bağımsız değişken gerektirir **omp_nest_lock_t** türü.

- `omp_init_nest_lock` İşlevi nestable kilit başlatır.

- `omp_destroy_nest_lock` İşlevi nestable kilit kaldırır.

- `omp_set_nest_lock` İşlevi nestable kilit kullanılabilir oluncaya kadar bekler.

- `omp_unset_nest_lock` İşlevi nestable kilit serbest bırakır.

- `omp_test_nest_lock` İşlevi test nestable kilit.

OpenMP kilit işlevleri kilit değişken bunlar her zaman okuyabilmesini ve en güncel kilit değişkenin değerini güncelleştirme emin bir şekilde erişin. Bu nedenle, açık dahil etmek bir OpenMP program için gerekli değildir **Temizleme** yönergelerini kilit değişkenin değeri farklı iş parçacıkları arasında tutarlı olduğundan emin olun. (İhtiyacı olabilir **Temizleme** diğer değişkenlerin değerlerini tutarlı hale getirmek için yönergeleri.)