---
title: "3. Çalışma Zamanı Kitaplığı işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f693c3ff8bc3e44d47f885b6fb4c0d09b36fdbde
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="3-run-time-library-functions"></a>3. Çalışma Zamanı Kitaplığı işlevleri
Bu bölümde OpenMP C ve C++ çalışma zamanı kitaplığı işlevleri açıklanmaktadır. Üstbilgi  **\<omp.h >** iki tür, veri erişimi eşitlemek için kullanılan işlevler kilitleyin denetlemek ve Paralel yürütme ortamı sorgulamak için kullanılan bazı işlevler bildirir.  
  
 Türü **omp_lock_t** bir nesne türü bir kilit kullanılabilir olduğunu temsil etme özelliğine sahiptir veya bir iş parçacığı bir kilit sahibi. Bu kilit denir *basit kilitleri*.  
  
 Türü **omp_nest_lock_t** ya da bu temsil etme özelliğine sahip bir nesne türü bir kilit kullanılabilir veya kimliğe iş parçacığının, sahibi kilit ve *sayısı iç içe geçme* (aşağıda açıklanmıştır). Bu kilit denir *nestable kilitleri*.  
  
 Kitaplık işlevleri "C" bağlantı ile dış işlevlerdir.  
  
 Bu bölümde açıklamaları aşağıdaki konulara ayrılır:  
  
-   Yürütme Ortamı işlevleri (bkz [bölüm 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) sayfasında 35).  
  
-   İşlevler kilitleyin (bkz [bölüm 3.2](../../parallel/openmp/3-2-lock-functions.md) sayfasında 41).