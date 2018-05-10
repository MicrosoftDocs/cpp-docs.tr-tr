---
title: 'Nasıl yapılır: call ve transformer sınıflarına iş işlevleri sağlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca7948a1258ac1b5193d379dd37f426360edc42e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Nasıl yapılır: call ve transformer Sınıflarına İş İşlevleri Sağlama
Bu konuda iş işlevleri sağlamak için çeşitli yollar gösterilmektedir [concurrency::call](../../parallel/concrt/reference/call-class.md) ve [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) sınıfları.  
  
 İlk örnek bir lambda ifadesi geçirmek nasıl gösterir bir `call` nesnesi. İkinci örnek işlevi nesnesine geçirmek nasıl gösterir bir `call` nesnesi. Üçüncü örnek bir sınıf yönteme bağlama gösterilmektedir bir `call` nesnesi.  
  
 Çizim için bu konudaki her örnek kullanan `call` sınıfı. Kullanan bir örnek `transformer` sınıfı için bkz: [nasıl yapılır: veri ardışık düzeninde transformer kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanmak için en yaygın yolu gösterir `call` sınıfı. Bu örnek bir lambda işleve geçirir `call` Oluşturucusu.  
  
 [!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
13 squared is 169.  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek önceki bir benzer kullandığı `call` işlev nesnesi (functor) ile birlikte sınıfı.  
  
 [!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]  
  
## <a name="example"></a>Örnek  

 Aşağıdaki örnek önceki bir benzer kullandığı [std::bind1st](../../standard-library/functional-functions.md#bind1st) ve [std::mem_fun](../../standard-library/functional-functions.md#mem_fun) bağlamak için işlevleri bir `call` bir sınıf yöntemi nesnesine.  

  
 Eğer bağlamak bu tekniği kullanın bir `call` veya `transformer` işlev çağırma işleci yerine belirli bir sınıf yöntemi nesnesine `operator()`.  
  
 [!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]  
  
 Ayrıca sonucu atayabilirsiniz `bind1st` için işlev bir [std::function](../../standard-library/function-class.md) nesne veya kullanmak `auto` aşağıdaki örnekte gösterildiği gibi anahtar sözcüğü,.  
  
 [!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `call.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc call.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Nasıl yapılır: veri ardışık düzeninde transformer kullanma](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [Çağrı sınıfı](../../parallel/concrt/reference/call-class.md)   
 [transformer Sınıfı](../../parallel/concrt/reference/transformer-class.md)
