---
title: "2.7.2.1 özel | Microsoft Docs"
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
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a08faf39ab2f82d76a936c216ba6707bee5c240
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="2721-private"></a>2.7.2.1 private
`private` Yan tümcesi bir ekip her iş parçacığı için özel olarak değişken listesinde değişkenleri bildirir. Söz dizimi `private` yan tümcesi aşağıdaki gibidir:  
  
```  
private(variable-list)  
```  
  
 Belirtilen değişken davranışını bir `private` yan tümcesi aşağıdaki gibidir. Otomatik depolama süre ile yeni bir nesne için yapı tahsis edilir. Yeni nesne hizalamasını ve boyutu değişkeni türüne göre belirlenir. Bu ayırma Ekipteki her bir iş parçacığı için bir kez gerçekleşir ve varsayılan bir oluşturucu sınıfı için bir nesne gerekirse çağrılır; Aksi takdirde ilk belirsiz değerdir.  Değişkeni tarafından başvurulan özgün nesne yapı girişte belirsiz bir değere sahip, yapı dinamik kapsam içinde değiştirilmemelidir ve yapı gelen Çıkışta belirsiz bir değere sahip.  
  
 Yönerge yapı sözcük kapsamını iş parçacığı tarafından ayrılan yeni özel nesne değişkenine başvuruyor.  
  
 Kısıtlamaları `private` yan tümcesi aşağıdaki gibidir:  
  
-   Belirtilen bir sınıf türü sahip bir değişken bir `private` yan tümcesi, erişilebilir, anlaşılır varsayılan oluşturucusu olmalıdır.  
  
-   Belirtilen değişken bir `private` yan tümcesi değil olmalıdır bir **const**-yazın bir sınıf olmadıkça türü tam bir `mutable` üye.  
  
-   Belirtilen değişken bir `private` yan tümcesi eksik bir türü veya bir başvuru türü değil olmalıdır.  
  
-   Görünen değişkenleri `reduction` yan tümcesinde bir **paralel** yönergesi belirtilemez bir `private` paralel yapı bağlar iş paylaşım bir yönergesi yan tümcesi.