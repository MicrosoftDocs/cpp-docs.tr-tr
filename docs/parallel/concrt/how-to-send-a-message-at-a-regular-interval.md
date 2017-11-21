---
title: "Nasıl yapılır: düzenli aralıkla ileti gönderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c5c10ba2a1fee400ef99799c7c83a3bdcacd084f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Nasıl yapılır: Düzenli Aralıkla İleti Gönderme
Bu örnek eşzamanlılık kullanmayı gösterir::[timer sınıfı](../../parallel/concrt/reference/timer-class.md) düzenli aralıklarla ileti göndermek için.  
  
## <a name="example"></a>Örnek  

 Aşağıdaki örnek kullanan bir `timer` uzun bir işlem sırasında ilerleme durumunu raporlamak nesnesi. Bu örnek bağlantılar `timer` nesnesine bir [concurrency::call](../../parallel/concrt/reference/call-class.md) nesnesi. `call` Nesne düzenli aralıklarla bir İlerleme göstergesi konsola yazdırır. [Concurrency::timer::start](reference/timer-class.md#start) yöntemi ayrı bir bağlamda Zamanlayıcı çalıştırır. `perform_lengthy_operation` İşlev çağrıları [concurrency::wait](reference/concurrency-namespace-functions.md#wait) uzun süren işlem benzetimini yapmak için ana içerik üzerinde işlevi.  

  
 [!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir:  
  
```Output  
Performing a lengthy operation..........done.  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `report-progress.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc rapor-progress.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [İleti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md)
