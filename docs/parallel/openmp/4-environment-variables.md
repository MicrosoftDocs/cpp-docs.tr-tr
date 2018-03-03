---
title: "4. Ortam değişkenleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cef1bac78afbcc8b852c3bd42e0904e1963137c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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