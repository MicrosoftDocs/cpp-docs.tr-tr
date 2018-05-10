---
title: 4. Ortam değişkenleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edd4f795a3511358d2b95b93e180b9b21b964dd2
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="4-environment-variables"></a>4. Ortam Değişkenleri
Bu bölümde, OpenMP C ve C++ API ortam değişkenlerini (veya eşdeğer platforma özgü mekanizmaları) açıklanmaktadır paralel kod yürütmeyi denetlemek.  Ortam değişkenlerinin adları büyük olmalıdır. Atanmış değerler büyük küçük harfe duyarlı ve baştaki ve sondaki boşluk olabilir.  Değerlerin program başlatıldıktan sonra yapılan değişiklikler göz ardı edilir.  
  
 Ortam değişkenleri aşağıdaki gibidir:  
  
-   **OMP_SCHEDULE** çalışma zamanı zamanlama türü ve öbek boyutunu belirler.  
  
-   **OMP_NUM_THREADS** yürütme sırasında kullanılacak iş parçacıklarının sayısını ayarlar.  
  
-   **Omp_dynamıc** etkinleştirir veya iş parçacığı sayısını dinamik olarak ayarlamayı devre dışı bırakır.  
  
-   **OMP_NESTED** etkinleştirir veya iç içe geçmiş paralellik devre dışı bırakır.  
  
 Bu bölümdeki örnekler yalnızca bu değişkenleri UNIX C Kabuğu (csh) ortamlarında nasıl ayarlanabilir gösterir. İçinde Korn kabuk ve DOS ortamları eylemleri benzer, aşağıdaki gibidir:  
  
 csh:  
 setenv OMP_SCHEDULE "dinamik"  
  
 ksh:  
 OMP_SCHEDULE dışarı aktarma "dinamik" =  
  
 DOS:  
 OMP_SCHEDULE Ayarla "dinamik" =