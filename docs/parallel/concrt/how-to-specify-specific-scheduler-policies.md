---
title: "Nasıl yapılır: belirli Zamanlayıcı ilkeleri belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- specifying scheduler policies [Concurrency Runtime]
- scheduler policies, specifying [Concurrency Runtime]
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0ca5172372a9a80c419e9be54b0378f1254f4e6a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-specify-specific-scheduler-policies"></a>Nasıl yapılır: Belirli Zamanlayıcı İlkeleri Belirtme
Zamanlayıcı ilkeleri Zamanlayıcısı görevleri yönettiğinde kullanan stratejisi denetlemenize olanak verir. Bu konu bir zamanlayıcı İlkesi bir İlerleme göstergesi konsola yazdırır bir görev iş parçacığı önceliğini artırmak için nasıl kullanılacağını gösterir.  
  
 Zaman uyumsuz aracılar ile birlikte özel Zamanlayıcı ilkelerini kullanan bir örnek için bkz: [nasıl yapılır: aracılar, kullanımı belirli Zamanlayıcı ilkeleri oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, paralel olarak iki görevleri gerçekleştirir. İlk görev n hesaplar<sup>th</sup> Fibonacci numarası. İkinci görev bir İlerleme göstergesi konsola yazdırır.  
  
 İlk görev özyinelemeli ayrıştırma Fibonacci sayısını hesaplamak için kullanır. Diğer bir deyişle, her görev yinelemeli olarak genel sonuç hesaplamak için görevleri oluşturur. Özyinelemeli ayrıştırma kullanan bir görev tüm kullanılabilir kaynakları kullanın ve böylece diğer görevleri tamamen Kaynaksız bırakabilir. Bu örnekte, bilgi işlem kaynakları zamanında erişimi İlerleme göstergesi yazdırır görev alamayabilir.  
  
 Bu örnek bir bilgi işlem kaynaklarına erişimi Orta ilerleme iletisi yazdırır görev sağlamak için açıklanan adımları kullanır [nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) özel bir ilke olan Zamanlayıcı örneğini oluşturmak için. Özel ilke en yüksek öncelik sınıf olmak için iş parçacığı önceliği belirtir.  
  
 Bu örnekte [concurrency::call](../../parallel/concrt/reference/call-class.md) ve [concurrency::timer](../../parallel/concrt/reference/timer-class.md) İlerleme göstergesi yazdırmak için sınıflar. Bu sınıfların başvuru ele kendi oluşturucular sürümlerine sahip bir [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) bunları zamanlar nesnesi. Örnek Fibonacci numarası ve İlerleme göstergesi yazdırır görev zamanlama Zamanlayıcı örneğini hesaplar görev zamanlamak için varsayılan Zamanlayıcısı'nı kullanır.  
  
 Özel bir ilke bir Zamanlayıcı kullanmanın avantajları göstermek için bu örnek iki kez genel görevi gerçekleştirir. Örnek, varsayılan Zamanlayıcı ilk iki görev zamanlama için kullanır. Örnek daha sonra ilk görevi zamanlamak için varsayılan Zamanlayıcı ve ikinci görev zamanlamak için özel bir ilke olan Zamanlayıcı'yı kullanır.  
  
 [!code-cpp[concrt-scheduler-policy#1](../../parallel/concrt/codesnippet/cpp/how-to-specify-specific-scheduler-policies_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
Default scheduler:  
...........................................................................done  
Scheduler that has a custom policy:  
...........................................................................done  
```  
  
 İki görevlerin aynı sonucu verir ancak özel bir ilke kullanan sürüm daha responsively davranması yükseltilmiş öncelikli olarak çalıştırmak için İlerleme göstergesi yazdırır görevi etkinleştirir.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `scheduler-policy.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc Zamanlayıcı-policy.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zamanlayıcı ilkeleri](../../parallel/concrt/scheduler-policies.md)   
 [Nasıl yapılır: Zamanlayıcı örneğini yönetme](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [Nasıl yapılır: belirli Zamanlayıcı ilkelerini kullanan aracılar oluşturma](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

