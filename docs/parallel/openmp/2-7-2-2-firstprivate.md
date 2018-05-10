---
title: 2.7.2.2 firstprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8e44ca52ba1f76d5b3791a1d08301bf06e7eab
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="2722-firstprivate"></a>2.7.2.2 firstprivate
**Firstprivate** yan tümcesi tarafından sağlanan işlevleri bir alt kümesi sağlar **özel** yan tümcesi. Söz dizimi **firstprivate** yan tümcesi aşağıdaki gibidir:  
  
```  
firstprivate(variable-list)  
```  
  
 Belirtilen değişkenleri *değişken listesi* sahip **özel** açıklandığı gibi yan tümcesinde semantiği [bölüm 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) sayfasında 25. Bir kez yapısı iş parçacığının yürütülmesi önce iş parçacığı başına yapıldığını gibi başlatma veya yapım olur. İçin bir **firstprivate** paralel yapı yan tümcesi, ilk yeni özel nesne değeri paralel yapı karşılaştığı iş parçacığı için hemen önce mevcut özgün nesnenin değeri. İçin bir **firstprivate** iş paylaşım yapı yan tümcesi, ilk iş paylaşım yapı yürütür her bir iş parçacığı için yeni özel nesnesi değeri süre önce noktası var özgün nesne değeri, iş parçacığı iş paylaşım yapı karşılaşır. Ayrıca, C++ nesneleri için her iş parçacığı için yeni özel nesnesi özgün nesnesinden oluşturulan kopyasıdır.  
  
 Kısıtlamaları **firstprivate** yan tümcesi aşağıdaki gibidir:  
  
-   Belirtilen değişken bir **firstprivate** yan tümcesi eksik bir türü veya bir başvuru türü değil olmalıdır.  
  
-   Olarak belirtilen bir sınıf türü sahip bir değişken **firstprivate** erişilebilir, anlaşılır kopyalama oluşturucuya sahip olmalıdır.  
  
-   Paralel bir bölge içinde özel olan veya görünen değişkenleri **azaltma** yan tümcesinde bir **paralel** yönergesi belirtilemez bir **firstprivate** yan tümcesi bir Paralel yapı bağlar iş paylaşım yönergesi.