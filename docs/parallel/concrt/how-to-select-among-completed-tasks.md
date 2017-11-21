---
title: "Nasıl yapılır: Tamamlanan görevler arasında seçim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a36e871c8cea0a1ed16362ab7d8683151fe17825
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-select-among-completed-tasks"></a>Nasıl yapılır: Tamamlanan Görevler Arasında Seçim Yapma
Bu örnek nasıl kullanılacağını gösterir [concurrency::choice](../../parallel/concrt/reference/choice-class.md) ve [concurrency::join](../../parallel/concrt/reference/join-class.md) sınıfları arama algoritması tamamlamak için ilk görevi seçin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iki arama algoritmasını paralel olarak gerçekleştirir ve tamamlamak için ilk algoritmasını seçer. Bu örnek tanımlar `employee` sayısal bir tanımlayıcı ve bir ücret çalışana ait tutar türü. `find_employee` İşlevi sağlanan tanımlayıcısı veya sağlanan maaş ilk çalışan bulur. `find_employee` İşlevi de sağlanan tanımlayıcısı'nı veya maaş hiçbir çalışan olduğu durumda işler. `wmain` İşlevi bir dizi oluşturur `employee` nesneleri ve birkaç tanımlayıcısı ve maaş değerleri arar.  
  
 Örnek kullanan bir `choice` nesne arasında aşağıdaki durumlarda seçin:  
  
1.  Sağlanan tanımlayıcı bir çalışan var.  
  
2.  Sağlanan maaş bir çalışan var.  
  
3.  Sağlanan tanımlayıcısı'nı veya maaş hiçbir çalışan var.  
  
 İlk iki durumlarda, örneğin kullanan bir [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) nesne tanımlayıcısı ve başka tutmak için `single_assignment` maaş tutacak nesne. Örnek kullanan bir `join` nesne üçüncü durumda. `join` Nesne ek iki oluşur `single_assignment` nesneleri, sağlanan tanımlayıcı hiçbir çalışan bulunduğu çalışması için diğeri için sağlanan maaş hiçbir çalışan bulunduğu durumda. `join` Nesne kendi üyelerinin her biri bir ileti alındığında bir ileti gönderir. Bu örnekte, `join` nesne sağlanan tanımlayıcı hiçbir çalışan olduğunda ileti gönderir veya maaş bulunmaktadır.  
  
 Örnek kullanan bir [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) hem arama algoritmaları paralel olarak çalıştırmak için nesne. Her arama görev birine Yazar `single_assignment` verilen çalışan var olup olmadığını belirtmek için nesneleri. Örnek kullanır [concurrency::receive](reference/concurrency-namespace-functions.md#receive) bir ileti içeren ilk arabelleği dizinini elde etmek için işlevi ve `switch` sonucu yazdırmak için blok.  
  
 [!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/cpp/how-to-select-among-completed-tasks_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
Employee with id 14758 has salary 27780.00.  
Employee with salary 29150.00 has id 84345.  
Employee with id 61935 has salary 29905.00.  
No employee has id 899 or salary 31223.00.  
```  
  
 Bu örnekte [concurrency::make_choice](reference/concurrency-namespace-functions.md#make_choice) oluşturmak için yardımcı işlevini `choice` nesneleri ve [concurrency::make_join](reference/concurrency-namespace-functions.md#make_join) oluşturmak için yardımcı işlevini `join` nesneleri.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `find-employee.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc Bul-employee.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [İleti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md)   
 [seçenek sınıfı](../../parallel/concrt/reference/choice-class.md)   
 [join sınıfı](../../parallel/concrt/reference/join-class.md)
