---
title: 3. Çalışma Zamanı Kitaplığı işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d747f775509c6b3b2b95be51d95ea937816d3cd1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="3-run-time-library-functions"></a>3. Çalışma Zamanı Kitaplığı işlevleri
Bu bölümde OpenMP C ve C++ çalışma zamanı kitaplığı işlevleri açıklanmaktadır. Üstbilgi  **\<omp.h >** iki tür, veri erişimi eşitlemek için kullanılan işlevler kilitleyin denetlemek ve Paralel yürütme ortamı sorgulamak için kullanılan bazı işlevler bildirir.  
  
 Türü **omp_lock_t** bir nesne türü bir kilit kullanılabilir olduğunu temsil etme özelliğine sahiptir veya bir iş parçacığı bir kilit sahibi. Bu kilit denir *basit kilitleri*.  
  
 Türü **omp_nest_lock_t** ya da bu temsil etme özelliğine sahip bir nesne türü bir kilit kullanılabilir veya kimliğe iş parçacığının, sahibi kilit ve *sayısı iç içe geçme* (aşağıda açıklanmıştır). Bu kilit denir *nestable kilitleri*.  
  
 Kitaplık işlevleri "C" bağlantı ile dış işlevlerdir.  
  
 Bu bölümde açıklamaları aşağıdaki konulara ayrılır:  
  
-   Yürütme Ortamı işlevleri (bkz [bölüm 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) sayfasında 35).  
  
-   İşlevler kilitleyin (bkz [bölüm 3.2](../../parallel/openmp/3-2-lock-functions.md) sayfasında 41).