---
title: 'Nasıl yapılır: düzenli aralıkla ileti gönderme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6903a7ec6b833f7591afe79dc91d453b3905cc79
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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
 [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)
