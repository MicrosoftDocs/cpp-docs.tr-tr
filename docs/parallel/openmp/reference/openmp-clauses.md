---
title: OpenMP yan tümceleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afd0a8f66f9b0d027671629998597955b3aa69e9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378341"
---
# <a name="openmp-clauses"></a>OpenMP Yan Tümceleri

Yan tümceleri OpenMP API çağrısında kullanılan bağlantılar sağlar.

Visual C++ aşağıdaki OpenMP yan tümceleri destekler:

|Yan Tümce|Açıklama|
|------------|-----------------|
|[copyin](../../../parallel/openmp/reference/copyin.md)|Ana iş parçacığının değere erişmek iş parçacığı sağlayan bir [threadprivate](../../../parallel/openmp/reference/threadprivate.md) değişkeni.|
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|Bir veya daha fazla değişkenlerini tüm iş parçacıkları arasında paylaşılan olduğunu belirtir.|
|[default](../../../parallel/openmp/reference/default-openmp.md)|Bir paralel bölgenin içinde kapsamsız değişkenleri davranışını belirtir.|
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|Paralel yapı önce mevcut olduğundan, her iş parçacığı bir değişkenin kendi örneği olmalıdır ve değişken değişkenin değerini ile başlatılmalıdır belirtir.|
|[Eğer](../../../parallel/openmp/reference/if-openmp.md)|Bir döngü paralel veya seri gerçekleştirilip gerçekleştirilmeyeceğini belirtir.|
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|Değişkeni kapsayan bir bağlamın sürümü hangi iş parçacığının son yineleme (for-döngüsü yapısı) ya da son bölümdeki (#pragma bölümleri) yürüten özel sürümüne eşit ayarlandığını belirtir.|
|[nowait](../../../parallel/openmp/reference/nowait.md)|Bir yönergesinde örtük engel geçersiz kılar.|
|[num_threads](../../../parallel/openmp/reference/num-threads.md)|Bir iş parçacığı takıma iş parçacığı sayısını ayarlar.|
|[Sıralı](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|Üzerinde paralel gerekli [için](../../../parallel/openmp/reference/for-openmp.md) deyimi, bir [sıralı](../../../parallel/openmp/reference/ordered-openmp-directives.md) yönergesiyse döngüde kullanılacak.|
|[private](../../../parallel/openmp/reference/private-openmp.md)|Her iş parçacığı bir değişkenin kendi örnek olması gerektiğini belirtir.|
|[reduction](../../../parallel/openmp/reference/reduction.md)|Her iş parçacığı için özel bir veya daha fazla değişken bir paralel bölgenin sonunda azaltma işlemi konusunu olduğunu belirtir.|
|[schedule](../../../parallel/openmp/reference/schedule.md)|Uygulandığı [için](../../../parallel/openmp/reference/for-openmp.md) yönergesi.|
|[Paylaşılan](../../../parallel/openmp/reference/shared-openmp.md)|Bir veya daha fazla değişkenlerini tüm iş parçacıkları arasında paylaşılan olduğunu belirtir.|

## <a name="see-also"></a>Ayrıca Bkz.

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)<br/>
[Yönergeler](../../../parallel/openmp/reference/openmp-directives.md)